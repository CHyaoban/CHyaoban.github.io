# CHyaoban.github.io
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>欢迎页面</title>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
            font-family: 'Microsoft YaHei', Arial, sans-serif;
        }
        body {
            background-image: url('index.jpg');
            background-size: cover;
            background-position: center;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .container {
            background-color: transparent;
            border-radius: 20px;
            display: grid;
            grid-template-columns: 1fr 2fr;
            grid-template-rows: auto 1fr auto;
            gap: 30px;
            padding: 30px;
            width: 90%;
            max-width: 1200px;
            height: 80vh;
        }
        .clock {
            grid-column: 1;
            grid-row: 1;
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.5);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            font-size: 1.8em;
        }
        .welcome {
            grid-column: 2;
            grid-row: 1;
            font-size: 2.5em;
            display: flex;
            align-items: center;
            color: white;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
            background-color: rgba(0, 0, 0, 0.3);
            padding: 10px;
            border-radius: 10px;
        }
        .main-buttons {
            grid-column: 2;
            grid-row: 2 / span 2;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }
        .motto {
            grid-column: 1;
            grid-row: 2;
            font-style: italic;
            color: white;
            text-align: center;
            font-size: 1.5em;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
            background-color: rgba(0, 0, 0, 0.3);
            padding: 10px;
            border-radius: 10px;
        }
        .sub-buttons {
            grid-column: 1;
            grid-row: 3;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
        }
        button {
            padding: 15px;
            border: none;
            background-color: rgba(76, 175, 80, 0.5);
            color: white;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1.2em;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.3);
        }
        button:hover {
            background-color: rgba(76, 175, 80, 0.7);
            transform: scale(1.05);
        }
        .sub-buttons button {
            background-color: rgba(0, 140, 186, 0.5);
            font-size: 1em;
        }
        .sub-buttons button:hover {
            background-color: rgba(0, 140, 186, 0.7);
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="clock" id="clock">
            <div id="time"></div>
            <div id="date"></div>
        </div>
        <div class="welcome">欢迎来到这个网页</div>
        <div class="main-buttons">
            <button>按钮1</button>
            <button>按钮2</button>
            <button>按钮3</button>
            <button>按钮4</button>
            <button>按钮5</button>
            <button>按钮6</button>
        </div>
        <div class="motto">我本楚狂人，凤歌笑孔丘。韶华正茂岁方长，何惧风霜试剑芒。</div>
        <div class="sub-buttons">
            <button>小按钮1</button>
            <button>小按钮2</button>
            <button>小按钮3</button>
            <button>小按钮4</button>
            <button>小按钮5</button>
            <button>小按钮6</button>
        </div>
    </div>

    <script>
        function updateClock() {
            const now = new Date();
            const timeElement = document.getElementById('time');
            const dateElement = document.getElementById('date');
            
            const hours = String(now.getHours()).padStart(2, '0');
            const minutes = String(now.getMinutes()).padStart(2, '0');
            const seconds = String(now.getSeconds()).padStart(2, '0');
            
            timeElement.textContent = `${hours}:${minutes}:${seconds}`;
            dateElement.textContent = now.toLocaleDateString('zh-CN');
        }

        setInterval(updateClock, 1000);
        updateClock(); // 立即更新时钟
    </script>
</body>
</html>
