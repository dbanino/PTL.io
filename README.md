# PTL.io
<!DOCTYPE html>
<html>
  <head>
    <title>Countdown Timer</title>
    <script>
      function countdown() {
        const endDate = new Date("2025-07-01T00:00:00").getTime();
        const now = new Date().getTime();
        const distance = endDate - now;

        if (distance < 0) {
          document.getElementById("timer").innerHTML = "🎉 Time's up!";
          return;
        }

        const days = Math.floor(distance / (1000 * 60 * 60 * 24));
        const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
        const seconds = Math.floor((distance % (1000 * 60)) / 1000);

        document.getElementById("timer").innerHTML =
          `${days}d ${hours}h ${minutes}m ${seconds}s`;

        setTimeout(countdown, 1000);
      }

      window.onload = countdown;
    </script>
  </head>
  <body>
    <h1>Countdown to the World Cup Final</h1>
    <h2 id="timer"></h2>
  </body>
</html>
