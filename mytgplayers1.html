<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>LAYN Player</title>
    <style>
        :root {
            --tg-theme-bg-color: #000;
            --admin-panel-bg: #2c2c2e;
            --admin-panel-text: #fff;
            --admin-button-bg: #4d4d4f;
            --admin-button-hover: #5f5f61;
            --admin-title-color: #ff3b30;
            --admin-toggle-bg: #3c3c3e;
            --admin-toggle-on: #34c759;
            --category-active-color: #fff;
            --category-inactive-color: #8e8e93;
            --danger-color: #ff3b30;
            --success-color: #34c759;
            --cancel-button-bg: #555;
            --like-color: #ff2d55;
        }
        body, html {
            margin: 0; padding: 0; height: 100%; width: 100%;
            overflow: hidden; background-color: var(--tg-theme-bg-color);
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            user-select: none;
            color: #fff;
        }
        .hidden { display: none !important; }
        .auth-wall {
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            width: 100%;
            height: 100%;
            background-color: #1c1c1e;
            color: white;
            font-size: 18px;
            padding: 20px;
            box-sizing: border-box;
        }
        /* --- Category Bar --- */
        #category-selector {
            position: fixed; top: 15px; left: 50%;
            transform: translateX(-50%); z-index: 150; display: flex;
            gap: 15px; background-color: rgba(44, 44, 46, 0.7);
            padding: 8px 15px; border-radius: 20px; backdrop-filter: blur(10px);
            max-width: 90%; overflow-x: auto;
        }
        .category-btn {
            background: none; border: none; color: var(--category-inactive-color);
            font-size: 17px; font-weight: 600; cursor: pointer;
            padding: 5px; transition: color 0.3s; white-space: nowrap;
        }
        .category-btn.active { color: var(--category-active-color); }

        /* --- Video Player (TikTok Style) --- */
        #video-container {
            width: 100%; 
            height: var(--tg-viewport-height, 100vh); /* Адаптация под Telegram */
            overflow-y: scroll;
            scroll-snap-type: y mandatory;
            background-color: #000;
        }
        .video-section {
            width: 100%; 
            height: var(--tg-viewport-height, 100vh); /* Адаптация под Telegram */
            scroll-snap-align: start;
            position: relative; 
            display: flex;
            justify-content: center; 
            align-items: center; 
            cursor: pointer;
        }
        video { width: 100%; height: 100%; object-fit: cover; }
        .video-title {
            position: absolute; bottom: 15px; left: 15px; color: white;
            font-size: 18px; text-shadow: 2px 2px 4px rgba(0,0,0,0.7); z-index: 5;
        }
        .play-pause-icon {
            position: absolute; z-index: 10; width: 80px; height: 80px;
            display: flex; justify-content: center; align-items: center;
            pointer-events: none; opacity: 0; transform: scale(1.5);
            transition: opacity 0.2s ease-out, transform 0.2s ease-out;
        }
        .play-pause-icon.visible { opacity: 1; transform: scale(1); }

        /* --- Grid View Container --- */
        #grid-container {
            padding: 80px 10px 20px 10px;
            height: var(--tg-viewport-height, 100vh); /* Адаптация под Telegram */
            box-sizing: border-box;
            overflow-y: auto;
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
            gap: 15px;
        }
        .grid-item {
            cursor: pointer;
            position: relative;
        }
        .grid-item-poster {
            width: 100%;
            aspect-ratio: 2 / 3;
            border-radius: 8px;
            object-fit: cover;
            background-color: #222;
        }
        .grid-item-quality {
            position: absolute;
            top: 8px;
            right: 8px;
            background-color: rgba(0,0,0,0.7);
            color: #fff;
            padding: 2px 8px;
            border-radius: 5px;
            font-size: 12px;
            font-weight: bold;
        }
        .grid-item-title {
            font-size: 15px;
            font-weight: 600;
            margin-top: 8px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .grid-item-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 13px;
            color: #8e8e93;
            margin-top: 4px;
        }
        .grid-item-meta .views {
            display: flex;
            align-items: center;
            gap: 4px;
        }

        /* --- Side Menu --- */
        #side-menu {
            position: fixed; right: 10px; top: 50%;
            transform: translateY(-50%); display: flex;
            flex-direction: column; align-items: center; gap: 20px; z-index: 100;
        }
        .side-button {
            width: 50px; height: 50px; cursor: pointer; display: flex;
            flex-direction: column; justify-content: center; align-items: center;
            background-color: rgba(0, 0, 0, 0.4); border-radius: 50%;
            transition: background-color 0.2s; backdrop-filter: blur(5px);
        }
        .side-button:active { background-color: rgba(255, 255, 255, 0.3); }

        /* --- Modals --- */
        .modal {
            position: fixed; z-index: 200; left: 0; top: 0; width: 100%; height: 100%;
            background-color: rgba(0,0,0,0.85); display: none; justify-content: center; align-items: center;
            backdrop-filter: blur(8px);
        }
        .modal-content {
            background-color: #1c1c1e; padding: 20px; border-radius: 15px;
            width: 90%; max-width: 450px; position: relative;
            color: white;
        }
        .modal-content h3 { color: white; margin-top: 0; text-align: center; }
        .modal-content input, .modal-content select, .modal-content textarea, .modal-content button {
            width: 100%; padding: 12px; margin-bottom: 15px; border-radius: 8px; border: 1px solid #555;
            background-color: #333; color: white; box-sizing: border-box; font-size: 16px;
        }
        .modal-content button[type="submit"] { background-color: #007AFF; font-weight: bold; cursor: pointer; }
        .modal-content button.cancel-btn { background-color: var(--cancel-button-bg); }

        .close-button {
            position: absolute; top: 10px; right: 15px; color: #aaa;
            font-size: 28px; font-weight: bold; cursor: pointer;
        }
        
        /* --- Player Modal (New) --- */
        #player-modal .modal-content {
            background-color: #000;
            width: 100%;
            max-width: 95vw;
            height: auto;
            max-height: 95vh;
            padding: 0;
            overflow: hidden;
        }
        #player-modal-video {
            width: 100%;
            height: auto;
            max-height: 90vh;
            display: block;
        }
        #player-modal .close-button {
            z-index: 250;
            color: #fff;
            background-color: rgba(0,0,0,0.5);
            border-radius: 50%;
            width: 32px;
            height: 32px;
            display: flex;
            align-items: center;
            justify-content: center;
            line-height: 32px;
            top: 5px;
            right: 5px;
        }
        
        #video-form-modal .close-button,
        #category-form-modal .close-button,
        #ad-form-modal .close-button {
            display: none;
        }

        /* --- Admin Panel --- */
        .admin-panel-content {
            background-color: var(--admin-panel-bg); padding: 20px; border-radius: 20px;
            width: 90%; max-width: 320px; box-shadow: 0 10px 30px rgba(0,0,0,0.4);
        }
        .admin-header {
            display: flex; justify-content: space-between; align-items: center; margin-bottom: 25px;
        }
        .admin-header h2 { margin: 0; color: var(--admin-title-color); font-size: 24px; }
        .admin-section { margin-bottom: 20px; }
        .admin-section h3 { margin: 0 0 10px 0; color: var(--admin-panel-text); font-size: 16px; font-weight: 500; }
        .admin-buttons { display: flex; gap: 10px; }
        .admin-btn {
            flex: 1; padding: 10px; border: none; border-radius: 8px;
            background-color: var(--admin-button-bg); color: var(--admin-panel-text);
            font-size: 14px; cursor: pointer; transition: background-color 0.2s;
        }
        .admin-btn:hover { background-color: var(--admin-button-hover); }
        .admin-toggle { display: flex; justify-content: space-between; align-items: center; color: var(--admin-panel-text); }
        .switch { position: relative; display: inline-block; width: 51px; height: 31px; }
        .switch input { display: none; }
        .slider {
            position: absolute; cursor: pointer; top: 0; left: 0; right: 0; bottom: 0;
            background-color: var(--admin-toggle-bg); transition: .4s; border-radius: 34px;
        }
        .slider:before {
            position: absolute; content: ""; height: 27px; width: 27px;
            left: 2px; bottom: 2px; background-color: white;
            transition: .4s; border-radius: 50%;
        }
        input:checked + .slider { background-color: var(--admin-toggle-on); }
        input:checked + .slider:before { transform: translateX(20px); }

        /* --- Management List Style (for modals) --- */
        .management-list { list-style: none; padding: 0; max-height: 40vh; overflow-y: auto; }
        .list-item {
            background-color: #3a3a3c; padding: 10px 15px; border-radius: 8px;
            margin-bottom: 10px; display: flex; align-items: center; justify-content: space-between;
        }
        .list-item-name { flex-grow: 1; margin-right: 10px;}
        .list-item-controls { display: flex; gap: 8px; }
        .control-btn {
            background: none; border: none; cursor: pointer; padding: 5px;
        }
        .btn-edit { fill: #007AFF; } .btn-delete { fill: var(--danger-color); }
        .btn-toggle { fill: #34c759; } .btn-toggle.inactive { fill: #8e8e93; }

        /* --- Toast Notification --- */
        #toast-notification {
            position: fixed; top: 20px; left: 50%; transform: translateX(-50%);
            background-color: rgba(0, 0, 0, 0.8); color: white; padding: 12px 25px;
            border-radius: 25px; z-index: 999; opacity: 0; visibility: hidden;
            transition: all 0.3s; pointer-events: none;
        }
        #toast-notification.show { opacity: 1; visibility: visible; top: 30px; }
    </style>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
</head>
<body>
    
    <div id="app-container" class="hidden">
        <div id="category-selector"></div>
        
        <div id="video-container"></div>
        <div id="grid-container" class="hidden"></div>

        <div id="side-menu">
            <div id="sound-btn" class="side-button">
                <svg id="icon-sound-off" width="28" height="28" viewBox="0 0 24 24" fill="white"><path d="M3 9v6h4l5 5V4L7 9H3zm13.5 3c0-1.77-1.02-3.29-2.5-4.03v8.05c1.48-.73 2.5-2.25 2.5-4.02zM14 3.23v2.06c2.89.86 5 3.54 5 6.71s-2.11 5.85-5 6.71v2.06c4.01-.91 7-4.49 7-8.77s-2.99-7.86-7-8.77z"/></svg>
                <svg id="icon-sound-on" class="hidden" width="28" height="28" viewBox="0 0 24 24" fill="white"><path d="M3 9v6h4l5 5V4L7 9H3zm7-.17v6.34L7.83 13H5v-2h2.83L10 8.83zM16.5 12c0-1.77-1.02-3.29-2.5-4.03v8.05c1.48-.73 2.5-2.25 2.5-4.02zM14 3.23v2.06c2.89.86 5 3.54 5 6.71s-2.11 5.85-5 6.71v2.06c4.01-.91 7-4.49 7-8.77s-2.99-7.86-7-8.77z"/></svg>
            </div>
            <div id="like-btn" class="side-button">
                <svg id="icon-like-off" width="28" height="28" viewBox="0 0 24 24" fill="white"><path d="M16.5 3c-1.74 0-3.41.81-4.5 2.09C10.91 3.81 9.24 3 7.5 3 4.42 3 2 5.42 2 8.5c0 3.78 3.4 6.86 8.55 11.54L12 21.35l1.45-1.32C18.6 15.36 22 12.28 22 8.5 22 5.42 19.58 3 16.5 3zm-4.4 15.55l-.1.1-.1-.1C7.14 14.24 4 11.39 4 8.5 4 6.5 5.5 5 7.5 5c1.54 0 3.04.99 3.57 2.36h1.87C13.46 5.99 14.96 5 16.5 5c2 0 3.5 1.5 3.5 3.5 0 2.89-3.14 5.74-7.9 10.05z"/></svg>
                <svg id="icon-like-on" class="hidden" width="28" height="28" viewBox="0 0 24 24" fill="#ff2d55"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/></svg>
            </div>
            <div id="user-add-video-btn" class="side-button">
                <svg width="28" height="28" viewBox="0 0 24 24" fill="white"><path d="M12 4C11.4477 4 11 4.44772 11 5V11H5C4.44772 11 4 11.4477 4 12C4 12.5523 4.44772 13 5 13H11V19C11 19.5523 11.4477 20 12 20C12.5523 20 13 19.5523 13 19V13H19C19.5523 13 20 12.5523 20 12C20 11.4477 19.5523 11 19 11H13V5C13 4.44772 12.5523 4 12 4Z"/></svg>
            </div>
            <div id="admin-panel-btn" class="side-button">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="white"><path d="M12 1L3 5v6c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V5l-9-4zm0 10.99h7c-.53 4.12-3.28 7.79-7 8.94V12H5V6.3l7-3.11v8.8z"/></svg>
            </div>
        </div>
        
        <div id="user-upload-modal" class="modal">
            <div class="modal-content">
                <span class="close-button">&times;</span>
                <h3>Загрузить свое видео</h3>
                <form id="user-upload-form">
                    <input type="text" id="user-video-title" placeholder="Название видео" required>
                    <input type="file" id="user-video-file" accept="video/*" style="margin-top:5px;" required>
                    <button type="submit">Опубликовать</button>
                </form>
            </div>
        </div>

        <div id="admin-panel" class="modal">
            <div class="admin-panel-content">
                <div class="admin-header">
                    <h2>Админ-панель</h2>
                    <span id="admin-panel-close-btn" class="close-button">&times;</span>
                </div>
                <div class="admin-section">
                    <h3>Видео</h3>
                    <div class="admin-buttons">
                        <button id="admin-add-video-btn" class="admin-btn">Добавить</button>
                        <button id="admin-manage-videos-btn" class="admin-btn">Управлять</button>
                    </div>
                </div>
                <div class="admin-section">
                    <h3>Категории</h3>
                    <div class="admin-buttons">
                        <button id="admin-manage-categories-btn" class="admin-btn">Управлять</button>
                    </div>
                </div>
                <div class="admin-section">
                    <h3>Реклама</h3>
                    <div class="admin-buttons">
                        <button id="admin-add-ad-btn" class="admin-btn">Добавить</button>
                        <button id="admin-manage-ads-btn" class="admin-btn">Управлять</button>
                    </div>
                </div>
                <div class="admin-toggle">
                    <span>Запретить загрузку</span>
                    <label class="switch">
                        <input type="checkbox" id="admin-toggle-upload">
                        <span class="slider"></span>
                    </label>
                </div>
            </div>
        </div>

        <div id="video-form-modal" class="modal">
            <div class="modal-content">
                <span class="close-button">&times;</span>
                <h3 id="video-form-title">Добавить видео</h3>
                <form id="video-form">
                    <input type="hidden" id="video-id-input">
                    <input type="text" id="video-title-input" placeholder="Название видео" required>
                    <select id="video-category-select" required></select>
                    <input type="text" id="video-cover-input" placeholder="URL обложки (постера)">
                    <input type="text" id="video-duration-input" placeholder="Длительность (н-р, 105 min)">
                    <input type="text" id="video-quality-input" placeholder="Качество (н-р, HD)">
                    <select id="video-source-select" required>
                        <option value="url">Ссылка (прямая, Я.Диск, G.Drive)</option>
                        <option value="file">Файл с устройства</option>
                    </select>
                    <input type="text" id="video-url-input" placeholder="URL видео">
                    <input type="file" id="video-file-input" class="hidden" accept="video/*">
                    <button type="submit">Сохранить</button>
                    <button type="button" id="video-form-cancel-btn" class="cancel-btn">Отмена</button>
                </form>
            </div>
        </div>

        <div id="management-modal" class="modal">
            <div class="modal-content">
                <span id="management-modal-close-btn" class="close-button">&times;</span>
                <h3 id="management-title">Управление</h3>
                <ul id="management-list" class="management-list"></ul>
                <button id="management-add-new-btn">Добавить</button>
            </div>
        </div>

        <div id="category-form-modal" class="modal">
            <div class="modal-content">
                <span class="close-button">&times;</span>
                <h3 id="category-form-title">Добавить категорию</h3>
                <form id="category-form">
                    <input type="hidden" id="category-id-input">
                    <input type="text" id="category-name-input" placeholder="Название категории" required>
                    <button type="submit">Сохранить</button>
                    <button type="button" id="category-form-cancel-btn" class="cancel-btn">Отмена</button>
                </form>
            </div>
        </div>

        <div id="ad-form-modal" class="modal">
            <div class="modal-content">
                <span class="close-button">&times;</span>
                <h3 id="ad-form-title">Добавить рекламу</h3>
                <form id="ad-form">
                    <input type="hidden" id="ad-id-input">
                    <select id="ad-type-select" required>
                        <option value="image">Фото</option>
                        <option value="video">Видео</option>
                        <option value="code">HTML-код</option>
                    </select>
                    <input type="text" id="ad-source-input" placeholder="URL фото/видео" required>
                    <textarea id="ad-code-input" placeholder="Вставьте HTML-код" class="hidden"></textarea>
                    <input type="text" id="ad-desc-input" placeholder="Описание рекламы">
                    <input type="text" id="ad-btn-text-input" placeholder="Текст на кнопке">
                    <input type="text" id="ad-btn-link-input" placeholder="Ссылка для кнопки">
                    <button type="submit">Сохранить</button>
                    <button type="button" id="ad-form-cancel-btn" class="cancel-btn">Отмена</button>
                </form>
            </div>
        </div>
        
        <div id="player-modal" class="modal">
            <div class="modal-content">
                <span id="player-modal-close-btn" class="close-button">&times;</span>
                <video id="player-modal-video" controls playsinline></video>
            </div>
        </div>

        <div id="toast-notification"></div>
    </div>
    
    <div id="auth-container" class="hidden">
        <div class="auth-wall">
            Пожалуйста, откройте это приложение в Telegram.
        </div>
    </div>


    <svg width="0" height="0" class="hidden">
        <symbol id="icon-edit" viewBox="0 0 24 24"><path d="M17.25 2.75a.968.968 0 0 0-.71.29l-9.96 9.96-1.23 4.89a.968.968 0 0 0 1.2 1.2l4.89-1.23 9.96-9.96a.968.968 0 0 0 0-1.36L18 .29a.968.968 0 0 0-.75-.29zM16.5 4.5l2 2-8.5 8.5-2.83.71.71-2.83L16.5 4.5z"/></symbol>
        <symbol id="icon-delete" viewBox="0 0 24 24"><path d="M16 9v10H8V9h8m-1.5-6h-5l-1 1H5v2h14V4h-3.5l-1-1zM18 7H6v12c0 1.1.9 2 2 2h8c1.1 0 2-.9 2-2V7z"/></symbol>
        <symbol id="icon-play" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></symbol>
        <symbol id="icon-pause" viewBox="0 0 24 24"><path d="M6 19h4V5H6v14zm8-14v14h4V5h-4z"/></symbol>
        <symbol id="icon-eye" viewBox="0 0 24 24" fill="currentColor"><path d="M12 4.5C7 4.5 2.73 7.61 1 12c1.73 4.39 6 7.5 11 7.5s9.27-3.11 11-7.5C21.27 7.61 17 4.5 12 4.5zm0 10c-2.48 0-4.5-2.02-4.5-4.5S9.52 5.5 12 5.5s4.5 2.02 4.5 4.5-2.02 4.5-4.5 4.5zm0-7a2.5 2.5 0 1 0 0 5a2.5 2.5 0 0 0 0-5z"></path></symbol>
    </svg>

    <script>
    document.addEventListener('DOMContentLoaded', () => {
    
        const appContainer = document.getElementById('app-container');
        const authContainer = document.getElementById('auth-container');

        if (!window.Telegram || !window.Telegram.WebApp || !window.Telegram.WebApp.initData) {
            authContainer.classList.remove('hidden');
            return; 
        }

        appContainer.classList.remove('hidden');
        
        const tg = window.Telegram.WebApp;
        tg.ready();
        tg.expand();
        tg.setHeaderColor('#000000');
        tg.setBackgroundColor('#000000');

        const appData = {
            videos: [
                {id: 5, title: "Дэдпул и Росомаха", url: "https://files.catbox.moe/cs63e2.mp4", categoryId: 101, views: 1100, liked: false, coverUrl: "https://www.themoviedb.org/t/p/w600_and_h900_bestv2/v1Yv1rgn23aI1cM2ll08p8s2T3.jpg", duration: "174 min", quality: "CAM"},
                {id: 6, title: "Гадкий я 4", url: "https://files.catbox.moe/7vskkg.mp4", categoryId: 101, views: 506, liked: false, coverUrl: "https://www.themoviedb.org/t/p/w600_and_h900_bestv2/tMeGza0xMVA6Tz2a6x9DqgG23a.jpg", duration: "85 min", quality: "HD"},
                {id: 7, title: "Бордерлендс", url: "https://files.catbox.moe/06jt4x.mp4", categoryId: 101, views: 229, liked: false, coverUrl: "https://www.themoviedb.org/t/p/w600_and_h900_bestv2/tsoiKOt7iQiJ26y1Svt2zD9GkC.jpg", duration: "105 min", quality: "SD"},
                {id: 8, title: "Битлджус Битлджус", url: "https://files.catbox.moe/bh7av4.mp4", categoryId: 101, views: 204, liked: false, coverUrl: "https://www.themoviedb.org/t/p/w600_and_h900_bestv2/qO25C4TsdYLaeJdCoSCgeiugO2.jpg", duration: "177 min", quality: "WEBDL"},
                {id: 1, title: "Горный пейзаж", url: "https://files.catbox.moe/7vskkg.mp4", categoryId: 1, views: 150, liked: false, coverUrl: "https://images.pexels.com/photos/3889853/pexels-photo-3889853.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1", duration: "1 min", quality: "4K"},
                {id: 2, title: "Абстракция", url: "https://files.catbox.moe/06jt4x.mp4", categoryId: 2, views: 80, liked: true, coverUrl: "https://images.pexels.com/photos/2693212/pexels-photo-2693212.png?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1", duration: "2 min", quality: "HD"},
                {id: 3, title: "Город ночью", url: "https://files.catbox.moe/bh7av4.mp4", categoryId: 1, views: 200, liked: false, coverUrl: "https://images.pexels.com/photos/1105766/pexels-photo-1105766.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1", duration: "3 min", quality: "HD"},
                {id: 4, title: "Трейлер фильма", url: "https://files.catbox.moe/cs63e2.mp4", categoryId: 101, views: 500, liked: false, coverUrl: "https://images.pexels.com/photos/33129/popcorn-movie-party-entertainment.jpg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1", duration: "2 min", quality: "FHD"}
            ],
            categories: [
                {id: -1, name: "Рекомендации", parentId: null},
                {id: -2, name: "Любимые", parentId: null},
                {id: 3, name: "Видео", isParent: true, parentId: null},
                {id: 1, name: "Природа", parentId: null},
                {id: 2, name: "Арт", parentId: null},
                {id: 101, name: "Фильмы", parentId: 3},
                {id: 102, name: "Сериалы", parentId: 3}
            ],
            ads: [],
            settings: { userUploadsAllowed: true, adminPass: "1234" },
            state: {
                currentCategoryId: -1, viewingParentId: null, isMuted: true,
                currentActiveVideoElement: null, pressTimer: null, activeModal: null,
                videosToRender: [], currentVideoIndex: -1, isLoading: false,
            }
        };

        const dom = {
            videoContainer: document.getElementById('video-container'),
            gridContainer: document.getElementById('grid-container'),
            categorySelector: document.getElementById('category-selector'),
            sideMenu: document.getElementById('side-menu'),
            soundBtn: document.getElementById('sound-btn'),
            likeBtn: document.getElementById('like-btn'),
            iconLikeOn: document.getElementById('icon-like-on'),
            iconLikeOff: document.getElementById('icon-like-off'),
            iconSoundOn: document.getElementById('icon-sound-on'),
            iconSoundOff: document.getElementById('icon-sound-off'),
            userAddVideoBtn: document.getElementById('user-add-video-btn'),
            adminPanelBtn: document.getElementById('admin-panel-btn'),
            toast: document.getElementById('toast-notification'),
            playerModal: document.getElementById('player-modal'),
            playerModalVideo: document.getElementById('player-modal-video'),
            playerModalCloseBtn: document.getElementById('player-modal-close-btn'),
            userUploadModal: document.getElementById('user-upload-modal'),
            adminPanel: document.getElementById('admin-panel'),
            videoFormModal: document.getElementById('video-form-modal'),
            categoryFormModal: document.getElementById('category-form-modal'),
            adFormModal: document.getElementById('ad-form-modal'),
            managementModal: document.getElementById('management-modal'),
            userUploadForm: document.getElementById('user-upload-form'),
            userVideoTitle: document.getElementById('user-video-title'),
            userVideoFile: document.getElementById('user-video-file'),
            adminPanelCloseBtn: document.getElementById('admin-panel-close-btn'),
            adminAddVideoBtn: document.getElementById('admin-add-video-btn'),
            adminManageVideosBtn: document.getElementById('admin-manage-videos-btn'),
            adminManageCategoriesBtn: document.getElementById('admin-manage-categories-btn'),
            adminAddAdBtn: document.getElementById('admin-add-ad-btn'),
            adminManageAdsBtn: document.getElementById('admin-manage-ads-btn'),
            adminUploadToggle: document.getElementById('admin-toggle-upload'),
            videoForm: document.getElementById('video-form'),
            videoFormTitle: document.getElementById('video-form-title'),
            videoIdInput: document.getElementById('video-id-input'),
            videoTitleInput: document.getElementById('video-title-input'),
            videoCategorySelect: document.getElementById('video-category-select'),
            videoCoverInput: document.getElementById('video-cover-input'),
            videoDurationInput: document.getElementById('video-duration-input'),
            videoQualityInput: document.getElementById('video-quality-input'),
            videoSourceSelect: document.getElementById('video-source-select'),
            videoUrlInput: document.getElementById('video-url-input'),
            videoFileInput: document.getElementById('video-file-input'),
            videoFormCancelBtn: document.getElementById('video-form-cancel-btn'),
            categoryForm: document.getElementById('category-form'),
            categoryFormTitle: document.getElementById('category-form-title'),
            categoryIdInput: document.getElementById('category-id-input'),
            categoryNameInput: document.getElementById('category-name-input'),
            categoryFormCancelBtn: document.getElementById('category-form-cancel-btn'),
            adForm: document.getElementById('ad-form'),
            adFormTitle: document.getElementById('ad-form-title'),
            adIdInput: document.getElementById('ad-id-input'),
            adTypeSelect: document.getElementById('ad-type-select'),
            adSourceInput: document.getElementById('ad-source-input'),
            adCodeInput: document.getElementById('ad-code-input'),
            adDescInput: document.getElementById('ad-desc-input'),
            adBtnTextInput: document.getElementById('ad-btn-text-input'),
            adBtnLinkInput: document.getElementById('ad-btn-link-input'),
            adFormCancelBtn: document.getElementById('ad-form-cancel-btn'),
            managementModalCloseBtn: document.getElementById('management-modal-close-btn'),
            managementList: document.getElementById('management-list'),
            managementTitle: document.getElementById('management-title'),
            managementAddNewBtn: document.getElementById('management-add-new-btn'),
        };
        
        const isVideoCategoryActive = () => {
            const currentCat = appData.categories.find(c => c.id === appData.state.currentCategoryId);
            if (!currentCat) return false;
            return currentCat.parentId === 3 || currentCat.id === 3;
        }
        
        const formatViews = (views) => {
            if (views >= 1000) {
                return (views / 1000).toFixed(1).replace('.0', '') + 'K';
            }
            return views;
        }

        const showToast = (message) => {
            dom.toast.textContent = message;
            dom.toast.classList.add('show');
            setTimeout(() => dom.toast.classList.remove('show'), 2500);
        };

        const openModal = (modal) => {
            modal.style.display = 'flex';
            appData.state.activeModal = modal;
        };

        const closeModal = (modal) => {
            modal.style.display = 'none';
            if (appData.state.activeModal === modal) appData.state.activeModal = null;
        };

        const openPlayerModal = (videoData) => {
            if (!videoData.url || videoData.url === '#') {
                showToast("Для этого видео не указан источник");
                return;
            }
            dom.playerModalVideo.src = videoData.url;
            dom.playerModalVideo.poster = videoData.coverUrl;
            openModal(dom.playerModal);
            dom.playerModalVideo.play();
        };

        dom.playerModalCloseBtn.onclick = () => {
            closeModal(dom.playerModal);
            dom.playerModalVideo.pause();
            dom.playerModalVideo.src = '';
        };

        const renderCategories = () => {
            dom.categorySelector.innerHTML = '';
            
            const parentId = appData.state.viewingParentId;
            let categoriesToShow;

            if (parentId) {
                categoriesToShow = appData.categories.filter(c => c.parentId === parentId);
                const backBtn = document.createElement('button');
                backBtn.className = 'category-btn';
                backBtn.textContent = '← Назад';
                backBtn.onclick = () => {
                    appData.state.viewingParentId = null;
                    appData.state.currentCategoryId = parentId; 
                    renderAll();
                };
                dom.categorySelector.appendChild(backBtn);
            } else {
                 categoriesToShow = appData.categories.filter(c => !c.parentId)
                    .sort((a,b) => (a.id < 0 && b.id > 0) ? -1 : (a.id > 0 && b.id < 0) ? 1 : a.id - b.id);
            }
            
            categoriesToShow.forEach(cat => {
                const btn = document.createElement('button');
                btn.className = 'category-btn';
                btn.textContent = cat.name;
                btn.dataset.categoryId = cat.id;
                if (cat.id === appData.state.currentCategoryId) {
                    btn.classList.add('active');
                }
                btn.onclick = () => {
                    if (cat.isParent) {
                        appData.state.viewingParentId = cat.id;
                        const firstSubCategory = appData.categories.find(c => c.parentId === cat.id);
                        appData.state.currentCategoryId = firstSubCategory ? firstSubCategory.id : cat.id;
                    } else {
                        appData.state.currentCategoryId = cat.id;
                    }
                    renderAll();
                };
                dom.categorySelector.appendChild(btn);
            });
        };
        
        // --- НОВАЯ ЛОГИКА ДИНАМИЧЕСКОЙ ПРОГРУЗКИ ---
        const RENDER_BATCH_SIZE = 5;

        const createVideoSection = (videoData) => {
            const section = document.createElement('section');
            section.className = 'video-section';
            section.dataset.videoId = videoData.id;

            const video = document.createElement('video');
            video.src = videoData.url;
            if (videoData.coverUrl) video.poster = videoData.coverUrl;
            video.loop = true;
            video.playsInline = true;
            video.preload = 'metadata';

            const titleDiv = document.createElement('div');
            titleDiv.className = 'video-title';
            titleDiv.textContent = videoData.title;

            const playIcon = document.createElement('div');
            playIcon.className = 'play-pause-icon';
            playIcon.innerHTML = `<svg width="80" height="80" viewBox="0 0 24 24" fill="rgba(255,255,255,0.8)"><use href="#icon-play"></use></svg>`;

            section.onclick = () => {
                if (video.paused) { video.play(); playIcon.classList.remove('visible'); }
                else { video.pause(); playIcon.classList.add('visible'); }
            };

            section.append(video, titleDiv, playIcon);
            return section;
        };

        const loadMoreVideos = () => {
            if (appData.state.isLoading) return;

            const from = dom.videoContainer.children.length;
            const to = from + RENDER_BATCH_SIZE;
            const videosToLoad = appData.state.videosToRender.slice(from, to);

            if (videosToLoad.length === 0) return;

            appData.state.isLoading = true;
            videosToLoad.forEach(videoData => {
                const section = createVideoSection(videoData);
                dom.videoContainer.appendChild(section);
                observer.observe(section);
            });
            appData.state.isLoading = false;
        };
        
        dom.videoContainer.onscroll = () => {
            const { scrollTop, scrollHeight, clientHeight } = dom.videoContainer;
            if (scrollHeight - scrollTop - clientHeight < (clientHeight * 1.5)) { // Загружаем за 1.5 экрана до конца
                loadMoreVideos();
            }
        };

        const prepareVideoList = () => {
            dom.videoContainer.innerHTML = '';
            let videos = [];
            const catId = appData.state.currentCategoryId;

            if (catId === -1) { 
                videos = appData.videos.filter(v => v.views > 100).sort((a,b) => b.views - a.views);
            } else if (catId === -2) {
                videos = appData.videos.filter(v => v.liked);
            } else {
                videos = appData.videos.filter(v => v.categoryId === catId);
            }
            
            appData.state.videosToRender = videos;
            if (videos.length === 0) {
                 showToast("В этой категории пока нет видео");
            }
            loadMoreVideos(); // Загружаем первую партию
        };

        // --- КОНЕЦ НОВОЙ ЛОГИКИ ---

        const renderGridView = () => {
            dom.gridContainer.innerHTML = '';
            const videosToRender = appData.videos.filter(v => v.categoryId === appData.state.currentCategoryId);
            
            if (videosToRender.length === 0) {
                 showToast("В этой категории пока нет видео");
                 return;
            }

            videosToRender.forEach(videoData => {
                const item = document.createElement('div');
                item.className = 'grid-item';
                item.onclick = () => openPlayerModal(videoData);

                item.innerHTML = `
                    <img src="${videoData.coverUrl || 'https://via.placeholder.com/300x450/1a1a1a/000000?text=No+Image'}" alt="${videoData.title}" class="grid-item-poster">
                    <div class="grid-item-quality">${videoData.quality || ''}</div>
                    <h3 class="grid-item-title">${videoData.title}</h3>
                    <div class="grid-item-meta">
                        <span>${videoData.duration || ''}</span>
                        <span class="views">
                            <svg width="16" height="16"><use href="#icon-eye"></use></svg>
                            ${formatViews(videoData.views)}
                        </span>
                    </div>
                `;
                dom.gridContainer.appendChild(item);
            });
        };
        
        const renderAll = () => {
            renderCategories();
            
            if (isVideoCategoryActive()) {
                dom.videoContainer.classList.add('hidden');
                dom.gridContainer.classList.remove('hidden');
                dom.sideMenu.classList.add('hidden');
                renderGridView();
            } else {
                dom.gridContainer.classList.add('hidden');
                dom.videoContainer.classList.remove('hidden');
                dom.sideMenu.classList.remove('hidden');
                prepareVideoList(); // Используем новую функцию
            }
        }

        const updateLikeButtonState = (videoData) => {
            if (videoData) {
                dom.iconLikeOn.classList.toggle('hidden', !videoData.liked);
                dom.iconLikeOff.classList.toggle('hidden', videoData.liked);
            }
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                const videoElement = entry.target.querySelector('video');
                if (entry.isIntersecting) {
                    appData.state.currentActiveVideoElement = entry.target;
                    videoElement.muted = appData.state.isMuted;
                    videoElement.play().catch(() => {});
                    
                    const videoId = parseInt(entry.target.dataset.videoId);
                    const videoData = appData.videos.find(v => v.id === videoId);
                    
                    updateLikeButtonState(videoData);

                    if (videoData && !entry.target.viewCounted) {
                        videoData.views++;
                        entry.target.viewCounted = true; 
                    }

                } else {
                    videoElement.pause();
                    entry.target.viewCounted = false; 
                }
            });
        }, { threshold: 0.8 });
        
        // --- ОСТАЛЬНОЙ КОД БЕЗ ИЗМЕНЕНИЙ ---
        
        const openVideoForm = (video = null) => {
            dom.videoForm.reset();
            dom.videoIdInput.value = '';
            dom.videoUrlInput.classList.remove('hidden');
            dom.videoFileInput.classList.add('hidden');

            dom.videoCategorySelect.innerHTML = appData.categories
                .filter(c => c.id > 0 && !c.isParent) 
                .map(c => `<option value="${c.id}">${c.name}</option>`).join('');

            if (video) {
                dom.videoFormTitle.textContent = "Редактировать видео";
                dom.videoIdInput.value = video.id;
                dom.videoTitleInput.value = video.title;
                dom.videoUrlInput.value = video.url;
                dom.videoCoverInput.value = video.coverUrl || '';
                dom.videoDurationInput.value = video.duration || '';
                dom.videoQualityInput.value = video.quality || '';
                dom.videoCategorySelect.value = video.categoryId;
            } else {
                dom.videoFormTitle.textContent = "Добавить видео";
            }
            closeModal(dom.managementModal);
            openModal(dom.videoFormModal);
        };
        
        dom.videoForm.onsubmit = (e) => {
            e.preventDefault();
            const id = parseInt(dom.videoIdInput.value) || Date.now();
            const title = dom.videoTitleInput.value;
            const categoryId = parseInt(dom.videoCategorySelect.value);
            const coverUrl = dom.videoCoverInput.value;
            const duration = dom.videoDurationInput.value;
            const quality = dom.videoQualityInput.value;
            const source = dom.videoSourceSelect.value;
            const file = dom.videoFileInput.files[0];
            let url = dom.videoUrlInput.value;

            if (source === 'file' && file) {
                url = URL.createObjectURL(file);
            } else if (source === 'url' && !url) {
                showToast("Укажите URL видео");
                return;
            }

            const videoData = {
                title, categoryId, url, coverUrl, duration, quality
            };

            const existingIndex = appData.videos.findIndex(v => v.id === id);
            if (existingIndex > -1) {
                appData.videos[existingIndex] = { ...appData.videos[existingIndex], ...videoData };
            } else {
                appData.videos.push({ id, ...videoData, views: 0, liked: false });
            }

            closeModal(dom.videoFormModal);
            populateManagementList('videos');
            renderAll();
            showToast("Видео сохранено!");
        };

        dom.videoSourceSelect.onchange = (e) => {
            dom.videoUrlInput.classList.toggle('hidden', e.target.value === 'file');
            dom.videoFileInput.classList.toggle('hidden', e.target.value === 'url');
        };

        const openCategoryForm = (category = null) => {
            dom.categoryForm.reset();
            dom.categoryIdInput.value = '';
            if(category) {
                dom.categoryFormTitle.textContent = "Редактировать категорию";
                dom.categoryIdInput.value = category.id;
                dom.categoryNameInput.value = category.name;
            } else {
                dom.categoryFormTitle.textContent = "Добавить категорию";
            }
            closeModal(dom.managementModal);
            openModal(dom.categoryFormModal);
        }

        dom.categoryForm.onsubmit = (e) => {
            e.preventDefault();
            const id = parseInt(dom.categoryIdInput.value) || Date.now();
            const name = dom.categoryNameInput.value;
            
            const existingIndex = appData.categories.findIndex(c => c.id === id);
            if (existingIndex > -1) {
                appData.categories[existingIndex].name = name;
            } else {
                appData.categories.push({ id, name, parentId: null });
            }
            
            closeModal(dom.categoryFormModal);
            populateManagementList('categories');
            renderAll();
            showToast("Категория сохранена!");
        };

        const openAdForm = (ad = null) => {
            dom.adForm.reset();
            dom.adIdInput.value = '';
            handleAdTypeChange(); 

            if (ad) {
                dom.adFormTitle.textContent = "Редактировать рекламу";
                dom.adIdInput.value = ad.id;
                dom.adTypeSelect.value = ad.type;
                dom.adSourceInput.value = ad.source;
                dom.adCodeInput.value = ad.type === 'code' ? ad.source : '';
                dom.adDescInput.value = ad.description;
                dom.adBtnTextInput.value = ad.btnText;
                dom.adBtnLinkInput.value = ad.btnLink;
            } else {
                dom.adFormTitle.textContent = "Добавить рекламу";
            }
            handleAdTypeChange();
            closeModal(dom.managementModal);
            openModal(dom.adFormModal);
        };
        
        const handleAdTypeChange = () => {
             const isCode = dom.adTypeSelect.value === 'code';
             dom.adSourceInput.classList.toggle('hidden', isCode);
             dom.adCodeInput.classList.toggle('hidden', !isCode);
        };
        dom.adTypeSelect.onchange = handleAdTypeChange;

        dom.adForm.onsubmit = (e) => {
            e.preventDefault();
            const id = parseInt(dom.adIdInput.value) || Date.now();
            const type = dom.adTypeSelect.value;
            const source = type === 'code' ? dom.adCodeInput.value : dom.adSourceInput.value;

            const adData = {
                id, type, source,
                description: dom.adDescInput.value,
                btnText: dom.adBtnTextInput.value,
                btnLink: dom.adBtnLinkInput.value,
                active: true
            };
            
            const existingIndex = appData.ads.findIndex(a => a.id === id);
            if (existingIndex > -1) {
                adData.active = appData.ads[existingIndex].active; 
                appData.ads[existingIndex] = adData;
            } else {
                appData.ads.push(adData);
            }

            closeModal(dom.adFormModal);
            populateManagementList('ads');
            showToast("Реклама сохранена!");
        };

        const populateManagementList = (type) => {
            dom.managementList.innerHTML = '';
            let dataList, itemRenderer;
            
            const createControls = (item, itemType) => {
                const controls = document.createElement('div');
                controls.className = 'list-item-controls';
                
                if(itemType === 'ads'){
                     const toggleBtn = document.createElement('button');
                     toggleBtn.className = `control-btn btn-toggle ${item.active ? '' : 'inactive'}`;
                     toggleBtn.innerHTML = `<svg width="22" height="22"><use href="${item.active ? '#icon-pause' : '#icon-play'}"></use></svg>`;
                     toggleBtn.onclick = () => {
                         item.active = !item.active;
                         populateManagementList('ads');
                     };
                     controls.appendChild(toggleBtn);
                }

                const editBtn = document.createElement('button');
                editBtn.className = 'control-btn btn-edit';
                editBtn.innerHTML = '<svg width="20" height="20"><use href="#icon-edit"></use></svg>';
                editBtn.onclick = () => {
                    if(itemType === 'videos') openVideoForm(item);
                    if(itemType === 'categories') openCategoryForm(item);
                    if(itemType === 'ads') openAdForm(item);
                };
                
                const deleteBtn = document.createElement('button');
                deleteBtn.className = 'control-btn btn-delete';
                deleteBtn.innerHTML = '<svg width="20" height="20"><use href="#icon-delete"></use></svg>';
                deleteBtn.onclick = () => {
                    if (!confirm(`Вы уверены, что хотите удалить "${item.title || item.name || item.description || 'этот элемент'}"?`)) return;
                    
                    if(itemType === 'videos') appData.videos = appData.videos.filter(v => v.id !== item.id);
                    if(itemType === 'categories') {
                        if(item.id < 0) {
                            showToast("Системные категории удалять нельзя.");
                            return;
                        }
                        const childrenIds = appData.categories.filter(c => c.parentId === item.id).map(c => c.id);
                        const allIdsToDelete = [item.id, ...childrenIds];
                        
                        appData.categories = appData.categories.filter(c => !allIdsToDelete.includes(c.id));
                        appData.videos = appData.videos.filter(v => !allIdsToDelete.includes(v.categoryId)); 
                        
                        if (allIdsToDelete.includes(appData.state.currentCategoryId)) {
                           appData.state.currentCategoryId = -1;
                           appData.state.viewingParentId = null;
                        }
                    }
                    if(itemType === 'ads') appData.ads = appData.ads.filter(a => a.id !== item.id);
                    
                    populateManagementList(itemType);
                    renderAll();
                };

                controls.append(editBtn, deleteBtn);
                return controls;
            };

            switch (type) {
                case 'videos':
                    dom.managementTitle.textContent = "Управление видео";
                    dom.managementAddNewBtn.onclick = () => openVideoForm();
                    dataList = appData.videos;
                    itemRenderer = (item) => `<span class="list-item-name">${item.title}</span>`;
                    break;
                case 'categories':
                    dom.managementTitle.textContent = "Управление категориями";
                    dom.managementAddNewBtn.onclick = () => openCategoryForm();
                    dataList = appData.categories;
                    itemRenderer = (item) => {
                        let prefix = '';
                        if (item.parentId) prefix = ' -- ';
                        if (item.isParent) prefix = '▶ ';
                        if (item.id < 0) prefix = '⚙️ ';
                        return `<span class="list-item-name">${prefix}${item.name}</span>`;
                    };
                    break;
                case 'ads':
                    dom.managementTitle.textContent = "Управление рекламой";
                    dom.managementAddNewBtn.onclick = () => openAdForm();
                    dataList = appData.ads;
                    itemRenderer = (item) => `<span class="list-item-name">${item.description || "Реклама без описания"}</span>`;
                    break;
            }

            dataList.forEach(item => {
                const li = document.createElement('li');
                li.className = 'list-item';
                li.innerHTML = itemRenderer(item);
                li.appendChild(createControls(item, type));
                dom.managementList.appendChild(li);
            });
            
            closeModal(dom.adminPanel);
            openModal(dom.managementModal);
        };
        
        document.addEventListener('contextmenu', event => event.preventDefault());

        dom.soundBtn.onclick = (e) => {
            e.stopPropagation();
            appData.state.isMuted = !appData.state.isMuted;
            const video = appData.state.currentActiveVideoElement?.querySelector('video');
            if (video) video.muted = appData.state.isMuted;
            dom.iconSoundOn.classList.toggle('hidden', appData.state.isMuted);
            dom.iconSoundOff.classList.toggle('hidden', !appData.state.isMuted);
        };
        
        dom.likeBtn.onclick = (e) => {
             e.stopPropagation();
             if (!appData.state.currentActiveVideoElement) return;

             const videoId = parseInt(appData.state.currentActiveVideoElement.dataset.videoId);
             const videoData = appData.videos.find(v => v.id === videoId);

             if(videoData) {
                videoData.liked = !videoData.liked;
                updateLikeButtonState(videoData);
                showToast(videoData.liked ? "Добавлено в любимые" : "Удалено из любимых");

                if(appData.state.currentCategoryId === -2 && !videoData.liked) {
                    renderAll();
                }
             }
        };

        dom.userAddVideoBtn.onclick = () => {
            openModal(dom.userUploadModal);
        };

        dom.userUploadForm.onsubmit = (e) => {
            e.preventDefault();
            const title = dom.userVideoTitle.value;
            const file = dom.userVideoFile.files[0];

            if (file && title) {
                let targetCategoryId = appData.state.currentCategoryId;
                const category = appData.categories.find(c => c.id === targetCategoryId);
                if (!category || category.id < 0 || category.isParent) {
                    targetCategoryId = 1; 
                }

                const newVideo = {
                    id: Date.now(),
                    title: `${title} (загружено)`,
                    url: URL.createObjectURL(file),
                    categoryId: targetCategoryId,
                    views: 0,
                    liked: false,
                    coverUrl: '',
                    duration: '',
                    quality: 'New'
                };
                appData.videos.push(newVideo);
                renderAll(); 
                dom.userUploadForm.reset();
                closeModal(dom.userUploadModal);
                showToast("Ваше видео успешно добавлено!");
            } else {
                showToast("Укажите название и выберите файл");
            }
        };

        const handleAdminPress = () => {
            appData.state.pressTimer = setTimeout(() => {
                const password = prompt("Введите пароль администратора:");
                if (password === appData.settings.adminPass) {
                    openModal(dom.adminPanel);
                } else if (password !== null) {
                    alert("Неверный пароль!");
                }
            }, 2000); 
        };
        const handleAdminRelease = () => clearTimeout(appData.state.pressTimer);
        dom.adminPanelBtn.addEventListener('mousedown', handleAdminPress);
        dom.adminPanelBtn.addEventListener('mouseup', handleAdminRelease);
        dom.adminPanelBtn.addEventListener('touchstart', (e) => { e.preventDefault(); handleAdminPress(); });
        dom.adminPanelBtn.addEventListener('touchend', handleAdminRelease);
        dom.adminPanelBtn.addEventListener('click', () => showToast("Удерживайте для входа"));

        dom.adminManageVideosBtn.onclick = () => populateManagementList('videos');
        dom.adminManageCategoriesBtn.onclick = () => populateManagementList('categories');
        dom.adminManageAdsBtn.onclick = () => populateManagementList('ads');
        dom.adminAddVideoBtn.onclick = () => { closeModal(dom.adminPanel); openVideoForm(); };
        dom.adminAddAdBtn.onclick = () => { closeModal(dom.adminPanel); openAdForm(); };
        
        dom.adminUploadToggle.checked = !appData.settings.userUploadsAllowed;
        dom.userAddVideoBtn.classList.toggle('hidden', !appData.settings.userUploadsAllowed);
        dom.adminUploadToggle.onchange = (e) => {
            appData.settings.userUploadsAllowed = !e.target.checked;
            dom.userAddVideoBtn.classList.toggle('hidden', !appData.settings.userUploadsAllowed);
            showToast(`Загрузка видео ${appData.settings.userUploadsAllowed ? 'разрешена' : 'запрещена'}`);
        };

        dom.adminPanelCloseBtn.onclick = () => closeModal(dom.adminPanel);
        dom.userUploadModal.querySelector('.close-button').onclick = () => closeModal(dom.userUploadModal);
        
        dom.managementModalCloseBtn.onclick = () => {
            closeModal(dom.managementModal);
            openModal(dom.adminPanel);
        };
        
        const createCancelHandler = (formModal, listType) => () => {
            closeModal(formModal);
            if (listType) populateManagementList(listType);
        };
        
        dom.videoFormCancelBtn.onclick = createCancelHandler(dom.videoFormModal, 'videos');
        dom.categoryFormCancelBtn.onclick = createCancelHandler(dom.categoryFormModal, 'categories');
        dom.adFormCancelBtn.onclick = createCancelHandler(dom.adFormModal, 'ads');
        
        renderAll();
    });
    </script>
</body>
</html>
