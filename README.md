<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Light/Dark Mode Switch</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
      background-color: #f8f8f8;
      color: #333;
      transition: background-color 0.5s, color 0.5s;
    }

    #switch-container {
      position: absolute;
      top: 20px;
      right: 20px;
      display: flex;
      align-items: center;
    }

    #switch-label {
      margin-right: 5px;
    }

    #mode-switch {
      position: relative;
      display: inline-block;
      width: 50px;
      height: 24px;
    }

    #mode-switch input {
      display: none;
    }

    #slider {
      position: absolute;
      cursor: pointer;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background-color: #ccc;
      transition: 0.4s;
      border-radius: 34px;
    }

    #slider:before {
      position: absolute;
      content: "";
      height: 18px;
      width: 18px;
      left: 3px;
      bottom: 3px;
      background-color: white;
      transition: 0.4s;
      border-radius: 50%;
    }

    input:checked + #slider {
      background-color: #2196F3;
    }

    input:checked + #slider:before {
      transform: translateX(26px);
    }

    #popup {
      display: none;
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      padding: 20px;
      background-color: #fff;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
      z-index: 1000;
    }
  </style>
</head>
<body>

<div id="switch-container">
  <label id="switch-label" for="mode-switch">Dark Mode</label>
  <div id="mode-switch">
    <input type="checkbox" id="switch-checkbox" checked>
    <div id="slider"></div>
  </div>
</div>

<div id="popup">
  <p>Hey, don't turn it off yet!</p>
  <a href="#" id="play-video">Play me</a>
</div>

<script>
  const switchCheckbox = document.getElementById('switch-checkbox');
  const popup = document.getElementById('popup');
  const playVideoLink = document.getElementById('play-video');

  switchCheckbox.addEventListener('change', function() {
    if (!this.checked) {
      // If user turns off the switch, automatically turn it back on
      this.checked = true;
      popup.style.display = 'block';
    }
  });

  playVideoLink.addEventListener('click', function(event) {
    event.preventDefault();
    playVideo();
  });

  function playVideo() {
    // Replace the video link with your own video link
    const videoLink = "https://www.dropbox.com/scl/fi/68m0mt8hljty1c8x9fpql/Yandere-Girl-Final.mp4?rlkey=b950xmzy9t5unehtfeuvu5l1z&dl=0";

    // Open the video in a new tab
    window.open(videoLink, '_blank');
  }
</script>

</body>
</html>
