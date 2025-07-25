<!DOCTYPE html>
<html lang="fa">
<head>
  <meta charset="UTF-8" />
  <title>پیام حضرت علی (ع) - عید غدیر</title>
  <style>
    body {
      margin: 0;
      font-family: 'Tahoma', sans-serif;
      background-image: url('https://cdn.nody.ir/files/2021/10/28/nody-%D8%B9%DA%A9%D8%B3-%D8%BA%D8%AF%DB%8C%D8%B1-%D8%AE%D9%85-1635452898.jpg');
      background-size: cover;
      background-position: center;
      min-height: 100vh;
      color: #4b2e05;
    }

    #start-screen, #main-content {
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      min-height: 100vh;
      padding: 20px;
      background-color: rgba(255,255,255,0.85);
    }

    #start-screen.active, #main-content.active {
      display: flex;
    }

    h1 {
      font-size: 2.2rem;
      margin-bottom: 20px;
      font-weight: bold;
      text-shadow: 1px 1px 4px #d97300;
    }

    .btn {
      background-color: #d97300;
      border: none;
      color: white;
      font-size: 1.4rem;
      padding: 12px 30px;
      border-radius: 12px;
      cursor: pointer;
      transition: background-color 0.3s ease;
      box-shadow: 0 4px 8px rgba(217, 115, 0, 0.6);
      margin: 10px;
      min-width: 160px;
    }

    .btn:hover {
      background-color: #b85e00;
    }

    .images {
      display: flex;
      justify-content: center;
      gap: 30px;
      margin-bottom: 30px;
      flex-wrap: wrap;
    }

    .images img {
      width: 300px;
      height: auto;
      border-radius: 15px;
      box-shadow: 0 6px 15px rgba(217, 115, 0, 0.5);
      transition: transform 0.3s ease;
    }

    .images img:hover {
      transform: scale(1.05);
    }

    #message {
      margin-top: 10px;
      font-size: 1.3rem;
      line-height: 1.6;
      max-width: 700px;
      background: #fff9f0cc;
      border-radius: 15px;
      padding: 20px 25px;
      box-shadow: 0 4px 12px rgba(217, 115, 0, 0.3);
      min-height: 140px;
      color: #5a3e1b;
      white-space: pre-line;
      transition: opacity 0.3s ease;
    }

    footer {
      margin-top: 40px;
      font-size: 0.9rem;
      color: #a77a1e;
      font-style: italic;
    }
  </style>
</head>
<body>

  <!-- صفحه آغاز -->
  <div id="start-screen" class="active">
    <h1>آماده‌ای که شروع کنیم؟ 😊</h1>
    <button class="btn" onclick="start()">💫 بزن بریم 💫</button>
  </div>

  <!-- محتوای اصلی -->
  <div id="main-content">
    <h1>دکمه را کلیک کن تا حضرت علی علیه‌السلام حرفی بهت بزنه<br>فقط قول بده بهش عمل کنی 🤲</h1>

    <div class="images">
      <img src="https://media.hamshahrionline.ir/d/2025/05/28/4/5192490.jpg?ts=1748462423000" alt="غدیر خم">
    </div>

    <div>
      <button class="btn" onclick="showRandomMessage()">✨ حضرت علی بگو ✨</button>
      <button class="btn" id="anotherBtn" onclick="showRandomMessage()" style="display: none;">🔄 یکی دیگه</button>
    </div>

    <div id="message">📜 نصیحت اینجا برات نشون داده می‌شه...</div>

    <footer>عید غدیر خم مبارک باد</footer>
  </div>

  <script>
    const messages = [
      `"دوست واقعی کسی است که تو را در خطاهایت یاری کند."
نهج‌البلاغه، حکمت ۲۸۲`,
      `"با مردم چنان رفتار کن که اگر مُردی، بر تو بگریند و اگر زنده بودی، مشتاق دیدارت باشند."
نهج‌البلاغه، نامه ۳۱`,
      `"مهربانی بر مردم، نیمی از ایمان است."
نهج‌البلاغه، حکمت ۲۱۹`,
      `"کسی که دل کسی را شاد کند، خدا را خوشحال کرده است."
(نقل مضمون از نهج‌البلاغه)`,
      `"دستانی که کمک می‌کنند، مقدس‌تر از لب‌هایی‌اند که دعا می‌کنند."
(نقل به مضمون از سخنان حضرت)`
    ];

    let hasClickedOnce = false;

    function start() {
      document.getElementById('start-screen').classList.remove('active');
      document.getElementById('main-content').classList.add('active');
    }

    function showRandomMessage() {
      const idx = Math.floor(Math.random() * messages.length);
      const messageDiv = document.getElementById('message');
      messageDiv.style.opacity = 0;
      setTimeout(() => {
        messageDiv.innerText = messages[idx];
        messageDiv.style.opacity = 1;
      }, 300);

      if (!hasClickedOnce) {
        document.getElementById('anotherBtn').style.display = 'inline-block';
        hasClickedOnce = true;
      }
    }
  </script>

</body>
</html>
