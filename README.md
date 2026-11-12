<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>สุขสันต์วันครบรอบ</title>
  <style>
    /* กำหนดตัวแปรสีตามภาพ Color Palette */
    :root {
      --pine-tree: #2A342B;
      --kombu-green: #354231;
      --dingley: #5C7859;
      --brandy: #DEC7A6;
      --pale-copper: #C08267;
      --bg-cream: #F5F2EB;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Kalam', 'Chakra Petch', 'Segoe UI', sans-serif;
    }

    body {
      background-color: var(--pine-tree);
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      padding: 20px;
    }

    /* การ์ดความรักตรงกลาง */
    .card {
      background: var(--bg-cream);
      width: 100%;
      max-width: 500px;
      padding: 40px 25px;
      border-radius: 24px;
      border: 3px solid var(--kombu-green);
      box-shadow: 0 12px 30px rgba(0, 0, 0, 0.3);
      text-align: center;
      position: relative;
    }

    /* ข้อความหัวข้อ */
    .title {
      font-size: 26px;
      font-weight: 700;
      color: var(--kombu-green);
      margin-bottom: 20px;
      line-height: 1.4;
    }

    .subtitle {
      font-size: 22px;
      color: var(--pale-copper);
      margin-bottom: 15px;
      font-weight: 600;
    }

    /* ช่องกรอกรหัสผ่าน */
    .input-group {
      margin: 25px 0;
    }

    .passcode-input {
      width: 100%;
      max-width: 220px;
      padding: 12px;
      text-align: center;
      font-size: 24px;
      letter-spacing: 8px;
      border: 2px solid var(--brandy);
      border-radius: 12px;
      outline: none;
      background-color: #ffffff;
      color: var(--pine-tree);
    }

    .passcode-input:focus {
      border-color: var(--dingley);
    }

    /* ปุ่มกด UNLOCK */
    .unlock-btn {
      background-color: var(--dingley);
      color: #ffffff;
      border: none;
      padding: 12px 35px;
      font-size: 16px;
      font-weight: 600;
      letter-spacing: 1px;
      border-radius: 20px;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(92, 120, 89, 0.4);
      transition: all 0.2s ease;
    }

    .unlock-btn:hover {
      background-color: var(--kombu-green);
      transform: translateY(-2px);
    }

    .unlock-btn:active {
      transform: scale(0.98);
    }

    /* ส่วนแสดงผลความรัก (หน้าสอง) */
    .content-screen {
      display: none;
      animation: fadeIn 0.8s ease-in-out;
    }

    /* การจัดวางรูปภาพตามภาพที่ 2 */
    .image-container {
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
      margin-top: 30px;
      gap: 10px;
    }

    .pig-img {
      width: 30%;
      height: auto;
      object-fit: contain;
    }

    .flower-img {
      width: 35%;
      height: auto;
      object-fit: contain;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>

  <div class="card">
    <!-- 1. หน้ากรอกรหัสผ่าน -->
    <div id="passcode-screen">
      <div class="title">สุขสันต์วันครบรอบ</div>
      <div class="input-group">
        <input 
          type="password" 
          id="passcode" 
          class="passcode-input" 
          placeholder="••••••" 
          maxlength="6" 
        />
      </div>
      <button class="unlock-btn" onclick="checkPasscode()">ปลดล็อก ♡</button>
    </div>

    <!-- 2. หน้าแสดงผลหลังกรอกรหัสผ่านถูกต้อง (140224) -->
    <div id="flower-screen" class="content-screen">
      <div class="title">สุขสันต์วันครบรอบนะ เรน</div>
      <div class="subtitle">รักมากๆ นะ</div>

      <!-- ส่วนของรูปภาพตามเลย์เอาต์ -->
      <div class="image-container">
        <!-- หมูตัวซ้าย -->
        <img src="pig-left.png" alt="Pig Left" class="pig-img" />
        
        <!-- ดอกไม้ตรงกลาง -->
        <img src="flowers.png" alt="Tulips" class="flower-img" />
        
        <!-- หมูตัวขวา -->
        <img src="pig-right.png" alt="Pig Right" class="pig-img" />
      </div>
    </div>
  </div>

  <script>
    function checkPasscode() {
      const input = document.getElementById('passcode').value;
      // รหัสผ่านตามที่กำหนดในรูปภาพ
      const correctPasscode = "140224"; 

      if (input === correctPasscode) {
        document.getElementById('passcode-screen').style.display = 'none';
        document.getElementById('flower-screen').style.display = 'block';
      } else {
        alert("รหัสผ่านไม่ถูกต้อง ลองใหม่อีกครั้งนะ ♡");
      }
    }
  </script>

</body>
</html>