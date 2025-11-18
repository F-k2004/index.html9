<!DOCTYPE html>
<html lang="fa">
<head>
  <meta charset="UTF-8">
  <title>⏰ ساعت دیجیتال زنده</title>
  <style>
    body {
      margin: 0;
      font-family: sans-serif;
      background: linear-gradient(135deg, #1e3c72, #2a5298);
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      color: white;
      text-align: center;
    }
    .clock {
      font-size: 60px;
      padding: 30px 60px;
      background: rgba(255,255,255,0.1);
      border-radius: 20px;
      box-shadow: 0 4px 25px rgba(0,0,0,0.3);
      backdrop-filter: blur(10px);
      animation: fadein 1.2s ease;
    }
    @keyframes fadein {
      0% { opacity: 0; transform: scale(0.8); }
      100% { opacity: 1; transform: scale(1); }
    }
    .date {
      margin-top: 20px;
      font-size: 22px;
      opacity: 0.85;
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="clock" id="clock">00:00:00</div>
    <div class="date" id="date"></div>
  </div>

  <script>
    function updateClock() {
      const now = new Date();

      let h = now.getHours().toString().padStart(2, "0");
      let m = now.getMinutes().toString().padStart(2, "0");
      let s = now.getSeconds().toString().padStart(2, "0");

      const clock = document.getElementById("clock");
      clock.textContent = `${h}:${m}:${s}`;

      const days = ["یکشنبه","دوشنبه","سه‌شنبه","چهارشنبه","پنجشنبه","جمعه","شنبه"];
      const months = ["فروردین","اردیبهشت","خرداد","تیر","مرداد","شهریور","مهر","آبان","آذر","دی","بهمن","اسفند"];

      const d = now.getDay();
      const day = now.getDate();
      const month = now.getMonth();
      const year = now.getFullYear();

      document.getElementById("date").textContent =
        `${days[d]} - ${day} ${months[month]} ${year}`;
    }

    setInterval(updateClock, 1000);
    updateClock();
  </script>

</body>
</html>
