<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>العد التنازلي لإطلاق الدورة</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f2f2f2;
      text-align: center;
      padding: 50px;
      direction: rtl;
    }

    h1 {
      font-size: 36px;
      color: #333;
    }

    #countdown {
      font-size: 48px;
      color: #ff6600;
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <h1>ترقبوا إطلاق الدورة قريبًا!</h1>
  <div id="countdown">جاري التحميل...</div>

  <script>
    const targetDate = new Date("July 1, 2025 00:00:00").getTime();

    const countdown = setInterval(() => {
      const now = new Date().getTime();
      const distance = targetDate - now;

      if (distance < 0) {
        clearInterval(countdown);
        document.getElementById("countdown").innerHTML = "انطلقت الدورة!";
        return;
      }

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      document.getElementById("countdown").innerHTML =
        `${days} يوم ${hours} ساعة ${minutes} دقيقة ${seconds} ثانية`;
    }, 1000);
  </script>

</body>
</html>
