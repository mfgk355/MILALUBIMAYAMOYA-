<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Признание Милуничке</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #ffe6e6;
            font-family: Arial, sans-serif;
        }
        
        .container {
            text-align: center;
            background-color: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
            max-width: 500px;
            width: 90%;
        }
        
        h1 {
            color: #ff4d6d;
            margin-bottom: 30px;
        }
        
        .buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
            position: relative;
        }
        
        button {
            padding: 10px 20px;
            font-size: 18px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        #yes-btn {
            background-color: #4CAF50;
            color: white;
        }
        
        #no-btn {
            background-color: #f44336;
            color: white;
            position: absolute;
        }
        
        #heart {
            font-size: 100px;
            color: #ff4d6d;
            display: none;
            margin-top: 20px;
            animation: heartbeat 1s infinite;
        }
        
        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Я тебя люблю, Милуничка, а ты меня?</h1>
        <div class="buttons">
            <button id="yes-btn">Да</button>
            <button id="no-btn">Нет</button>
        </div>
        <div id="heart">❤️</div>
    </div>

    <script>
        const yesBtn = document.getElementById('yes-btn');
        const noBtn = document.getElementById('no-btn');
        const heart = document.getElementById('heart');
        const container = document.querySelector('.container');
        
        yesBtn.addEventListener('click', function() {
            heart.style.display = 'block';
            noBtn.style.display = 'none';
            yesBtn.style.display = 'none';
        });
        
        noBtn.addEventListener('click', function() {
            // Получаем размеры контейнера и кнопки
            const containerRect = container.getBoundingClientRect();
            const noBtnRect = noBtn.getBoundingClientRect();
            
            // Вычисляем максимальные координаты для перемещения кнопки
            const maxX = containerRect.width - noBtnRect.width - 20;
            const maxY = containerRect.height - noBtnRect.height - 20;
            
            // Генерируем случайные координаты
            const randomX = Math.floor(Math.random() * maxX);
            const randomY = Math.floor(Math.random() * maxY);
            
            // Перемещаем кнопку
            noBtn.style.left = randomX + 'px';
            noBtn.style.top = randomY + 'px';
        });
    </script>
</body>
</html>
