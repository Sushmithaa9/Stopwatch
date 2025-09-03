# Stopwatch
NAME:S MANO SUSHMITHA
REG NO:212224040187

##CODE:
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Stopwatch⌛</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #041e3c;
      font-family: Arial, sans-serif;
    }
    .stopwatch {
      text-align: center;
      background: rgb(86, 151, 178);
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0px 4px 12px rgba(85, 40, 40, 0.2);
    }
    #display {
      font-size: 2.5rem;
      margin-bottom: 20px;
      letter-spacing: 2px;
    }
    button {
      padding: 10px 20px;
      margin: 5px;
      border: none;
      border-radius: 8px;
      font-size: 1rem;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover {
      opacity: 0.8;
    }
    #start {
      background: #35a138;
      color: white;
    }
    #pause {
      background: #FF9800;
      color: white;
    }
    #reset {
      background: #F44336;
      color: white;
    }
  </style>
</head>
<body>

  <div class="stopwatch">
    <div id="display">00 : 00 : 000</div>
    <button id="start">Start</button>
    <button id="pause">Pause</button>
    <button id="reset">Reset</button>
  </div>

  <script>
    let startTime, updatedTime, difference, tInterval;
    let running = false;

    const display = document.getElementById('display');
    const startBtn = document.getElementById('start');
    const pauseBtn = document.getElementById('pause');
    const resetBtn = document.getElementById('reset');

    function startTimer() {
      if (!running) {
        startTime = new Date().getTime() - (difference || 0);
        tInterval = setInterval(updateTime, 10);
        running = true;
      }
    }

    function pauseTimer() {
      if (running) {
        clearInterval(tInterval);
        difference = new Date().getTime() - startTime;
        running = false;
      }
    }

    function resetTimer() {
      clearInterval(tInterval);
      running = false;
      difference = 0;
      display.innerHTML = "00 : 00 : 000";
    }

    function updateTime() {
      updatedTime = new Date().getTime() - startTime;

      let minutes = Math.floor((updatedTime / (1000 * 60)) % 60);
      let seconds = Math.floor((updatedTime / 1000) % 60);
      let milliseconds = Math.floor(updatedTime % 1000);

      minutes = (minutes < 10) ? "0" + minutes : minutes;
      seconds = (seconds < 10) ? "0" + seconds : seconds;
      milliseconds = milliseconds.toString().padStart(3, "0");

      display.innerHTML = `${minutes} : ${seconds} : ${milliseconds}`;
    }

    startBtn.addEventListener("click", startTimer);
    pauseBtn.addEventListener("click", pauseTimer);
    resetBtn.addEventListener("click", resetTimer);
  </script>

</body>
</html>
```
##OUTPUT:

<img width="1919" height="1124" alt="image" src="https://github.com/user-attachments/assets/8a05b014-461b-476a-9579-d166e090f373" />

