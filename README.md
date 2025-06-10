<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>العد التنازلي لإطلاق الدورة</title>
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
    }
  </style>
</head>
<body>

  <h1>Solar Professional Engineer</h1>

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

  <script>
    const targetDate = new Date("July 1, 2025 00:00:00").getTime();

    const updateCountdown = () => {
      const now = new Date().getTime();
      const distance = targetDate - now;

      if (distance < 0) {
        document.querySelector(".countdown-container").innerHTML = "<h2>انطلقت الدورة!</h2>";
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
    };

    updateCountdown();
    setInterval(updateCountdown, 1000);
  </script>

</body>
</html>
