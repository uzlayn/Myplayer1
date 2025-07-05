<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Telegram Mini App</title>
  <style>
    * {
      box-sizing: border-box;
    }
    body {
      margin: 0;
      font-family: sans-serif;
      background-color: #111;
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .container {
      max-width: 480px;
      width: 100%;
      padding: 1rem;
      display: none;
    }
    .not-telegram {
      text-align: center;
      padding: 2rem;
    }
    .not-telegram a {
      display: inline-block;
      background: #0088cc;
      color: white;
      padding: 0.75rem 1.5rem;
      border-radius: 8px;
      text-decoration: none;
      margin-top: 1rem;
    }
    .video-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 0.5rem;
    }
    .video-player {
      position: relative;
      background-color: #000;
    }
    video {
      width: 100%;
      border-radius: 10px;
    }
    .controls {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 0.5rem;
    }
    .tabs {
      display: flex;
      justify-content: space-around;
      margin: 1rem 0;
    }
    .tabs button {
      background: none;
      border: none;
      color: #ccc;
      font-weight: bold;
      padding: 0.5rem;
      cursor: pointer;
    }
    .tabs button.active {
      color: #fff;
      border-bottom: 2px solid #fff;
    }
    .playlist-item {
      display: flex;
      align-items: center;
      padding: 0.5rem 0;
      border-bottom: 1px solid #333;
    }
    .playlist-item img {
      width: 40px;
      height: 40px;
      margin-right: 1rem;
      border-radius: 5px;
    }
    .add-btn {
      background-color: #222;
      border: none;
      color: white;
      font-size: 1.5rem;
      width: 100%;
      padding: 1rem;
      margin-top: 1rem;
      border-radius: 10px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <div class="not-telegram" id="notTelegram">
    <h2>Bu mini ilova faqat Telegram ichida ishlaydi</h2>
    <a href="https://t.me/UZLAYNUZ" target="_blank">@UZLAYNUZ kanaliga o‘tish</a>
  </div>
  <div class="container" id="telegramApp">
    <div class="video-header">
      <span>&larr; Video Title</span>
      <span>&#x1f4e4;</span>
    </div>
    <div class="video-player">
      <video id="video" controls poster="https://via.placeholder.com/480x270">
        <source src="https://path.to/video.mp4" type="video/mp4">
        Your browser does not support HTML5 video.
      </video>
    </div>
    <div class="controls">
      <div>
        <label for="quality">Quality:</label>
        <select id="quality">
          <option>Auto</option>
          <option>480p</option>
          <option>720p</option>
          <option>1080p</option>
        </select>
      </div>
      <button onclick="toggleFullscreen()">⛶</button>
    </div><div class="tabs">
  <button class="active">Sport</button>
  <button>Education</button>
  <button>Entertainment</button>
</div>

<div class="playlist">
  <div class="playlist-item">
    <img src="https://www.gstatic.com/images/branding/product/2x/drive_48dp.png" alt="">
    <div>
      <div>Sample Video</div>
      <div style="font-size: 0.8rem; color: #aaa;">Description</div>
    </div>
  </div>
  <div class="playlist-item">
    <img src="https://via.placeholder.com/40?text=FD" alt="">
    <div>
      <div>Sample Video</div>
      <div style="font-size: 0.8rem; color: #aaa;">Description</div>
    </div>
  </div>
  <div class="playlist-item">
    <img src="https://via.placeholder.com/40?text=YD" alt="">
    <div>
      <div>Sample Video</div>
      <div style="font-size: 0.8rem; color: #aaa;">Description</div>
    </div>
  </div>
</div>

<button class="add-btn">＋ Add Video</button>

  </div>  <script>
    function toggleFullscreen() {
      const video = document.getElementById('video');
      if (video.requestFullscreen) {
        video.requestFullscreen();
      } else if (video.webkitRequestFullscreen) {
        video.webkitRequestFullscreen();
      } else if (video.msRequestFullscreen) {
        video.msRequestFullscreen();
      }
    }

    // Telegram Mini App check
    window.addEventListener('DOMContentLoaded', function () {
      const isTelegram = navigator.userAgent.includes('Telegram');
      if (isTelegram) {
        document.getElementById('telegramApp').style.display = 'block';
        document.getElementById('notTelegram').style.display = 'none';
      } else {
        document.getElementById('telegramApp').style.display = 'none';
        document.getElementById('notTelegram').style.display = 'block';
      }
    });
  </script></body>
</html>
