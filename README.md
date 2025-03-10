# timer
2 minute timer
<div style="text-align:center; font-family: Arial, sans-serif;">
  <div id="timer" style="font-size:48px; margin-bottom:10px;">02:00</div>
  <button onclick="startTimer()" style="padding:8px 16px; font-size:16px; cursor:pointer;">Start Timer</button>
</div>

<script>
let duration = 120;
let timerInterval;

function startTimer() {
  clearInterval(timerInterval);
  let timeRemaining = duration;

  timerInterval = setInterval(function() {
    let minutes = Math.floor(timeRemaining / 60);
    let seconds = timeRemaining % 60;

    document.getElementById('timer').textContent =
      String(minutes).padStart(2, '0') + ':' + String(seconds).padStart(2, '0');

    if (--timeRemaining < 0) {
      clearInterval(timerInterval);
      alert('Time is up!');
    }
  }, 1000);
}

let duration = 120;
let timerInterval;
</script>
