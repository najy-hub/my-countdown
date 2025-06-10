<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>العد التنازلي المخصص</title>
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(to bottom, #141e30, #243b55);
      color: #fff;
      text-align: center;
      padding: 50px;
      direction: rtl;
    }

    h1 {
      font-size: 40px;
      margin-bottom: 40px;
    }

    .countdown-container {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
      margin-bottom: 40px;
    }

    .time-box {
      background-color: #1f2937;
      padding: 20px;
      border-radius: 10px;
      width: 100px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.3);
    }

    .time-box span {
      display: block;
      font-size: 36px;
      font-weight: bold;
      color: #00d1b2;
    }

    .time-label {
      margin-top: 10px;
      font-size: 16px;
      color: #ccc;
    }

    .btn-subscribe {
      background-color: #00d1b2;
      color: #fff;
      font-size: 20px;
      padding: 12px 30px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: background-color 0.3s ease;
      text-decoration: none;
      display: inline-block;
    }

    .btn-subscribe:hover {
      background-color: #00a896;
    }

    @media (max-width: 500px) {
      .time-box {
        width: 80px;
        padding: 15px;
      }

      .time-box span {
        font-size: 28px;
      }

      .time-label {
        font-size: 14px;
      }

      .btn-subscribe {
        font-size: 18px;
        padding: 10px 20px;
      }
    }
  </style>
</head>
<body>

  <h1>بقي على انتهاء العرض:</h1>

  <div class="countdown-container">
    <div class="time-box">
      <span id="days">00</span>
      <div class="time-label">أيام</div>
    </div>
    <div class="time-box">
      <span id="hours">00</span>
      <div class="time-label">ساعات</div>
    </div>
    <div class="time-box">
      <span id="minutes">00</span>
      <div class="time-label">دقائق</div>
    </div>
    <div class="time-box">
      <span id="seconds">00</span>
      <div class="time-label">ثواني</div>
    </div>
  </div>

  <!-- زر الاشتراك -->
  <a class="btn-subscribe" href="https://forms.gle/xHfeBsH9rEA19R3t5" target="_blank">اشترك الآن</a>

  <script>
    // نحسب الوقت المستهدف بإضافة 2 يوم + 6 ساعات + 30 دقيقة
    const now = new Date();
    const countdownDuration = (2 * 24 * 60 * 60 + 6 * 60 * 60 + 30 * 60) * 1000; // بالمللي ثانية
    const targetDate = new Date(now.getTime() + countdownDuration).getTime();

    function updateCountdown() {
      const now = new Date().getTime();
      const distance = targetDate - now;

      if (distance <= 0) {
        document.querySelector(".countdown-container").innerHTML = "<h2>انتهى الوقت!</h2>";
        return;
      }

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      document.getElementById("days").textContent = days.toString().padStart(2, '0');
      document.getElementById("hours").textContent = hours.toString().padStart(2, '0');
      document.getElementById("minutes").textContent = minutes.toString().padStart(2, '0');
      document.getElementById("seconds").textContent = seconds.toString().padStart(2, '0');
    }

    updateCountdown();
    setInterval(updateCountdown, 1000);
  </script>

</body>
</html>
