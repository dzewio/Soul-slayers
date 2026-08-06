# Soul-slayers
Клан сервера  an mine и других серверов их создатель Dzewio
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Клан Soul Slayers</title>
    <style>
        /* Современная тёмная игровая тема */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            text-align: center;
            margin: 0;
            padding: 50px 20px;
            background-color: #121214;
            color: #e1e1e6;
        }
        h1 {
            color: #ff3e3e;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 30px;
            text-shadow: 0 0 10px rgba(255, 62, 62, 0.3);
        }
        h2 {
            color: #ff8787;
        }
        .button {
            padding: 12px 24px;
            margin: 10px;
            cursor: pointer;
            background-color: #202024;
            color: #fff;
            border: 2px solid #ff3e3e;
            border-radius: 6px;
            font-weight: bold;
            transition: all 0.3s ease;
        }
        .button:hover {
            background-color: #ff3e3e;
            box-shadow: 0 0 15px rgba(255, 62, 62, 0.5);
            transform: translateY(-2px);
        }
        #content {
            margin-top: 30px;
            padding: 20px;
            background-color: #1a1a1e;
            border-radius: 8px;
            display: inline-block;
            min-width: 300px;
            border: 1px solid #29292e;
        }
        #messageForm {
            display: none;
            margin-top: 25px;
            background-color: #1a1a1e;
            padding: 20px;
            border-radius: 8px;
            inline-size: fit-content;
            margin-left: auto;
            margin-right: auto;
            border: 1px solid #29292e;
        }
        textarea {
            background-color: #121214;
            border: 1px solid #323238;
            color: #fff;
            padding: 10px;
            border-radius: 4px;
            resize: none;
            margin-bottom: 10px;
        }
        textarea:focus {
            outline: none;
            border-color: #ff3e3e;
        }
    </style>
</head>
<body>

    <h1>Добро пожаловать на сайт клана <br><span style="color: #fff;">Soul Slayers</span></h1>
    
    <nav>
        <button class="button" onclick="showMembers()">Участники</button>
        <button class="button" onclick="showAdmin()">Админ</button>
        <button class="button" onclick="toggleMessageForm()">Отправить заявку</button>
    </nav>

    <!-- Основной блок для вывода информации -->
    <div id="content">Здесь будет отображаться информация</div>

    <!-- Форма отправки заявки -->
    <div id="messageForm">
        <h2>Оставьте вашу заявку:</h2>
        <textarea id="message" rows="4" cols="50" placeholder="Расскажите о себе..."></textarea><br>
        <button class="button" onclick="submitMessage()">Отправить</button>
    </div>

    <script>
        // Главный блок контента
        const contentDiv = document.getElementById('content');
        const messageForm = document.getElementById('messageForm');

        function showMembers() {
            messageForm.style.display = 'none';
            contentDiv.innerHTML = '<h2>Участники:</h2><p>Пока нет участников</p>';
        }

        function showAdmin() {
            messageForm.style.display = 'none';
            contentDiv.innerHTML = '<h2>Админ:</h2><p>⚡ DZEWIO ⚡</p>';
        }

        function toggleMessageForm() {
            // Переключаем видимость формы
            if (messageForm.style.display === 'none' || messageForm.style.display === '') {
                messageForm.style.display = 'block';
                contentDiv.innerHTML = 'Заполнение заявки...';
            } else {
                messageForm.style.display = 'none';
                contentDiv.innerHTML = 'Ожидание действия';
            }
        }

        function submitMessage() {
            const messageInput = document.getElementById('message');
            const messageText = messageInput.value.trim();
            
            if (messageText === '') {
                alert('Пожалуйста, введите текст заявки!');
                return;
            }

            // Исправлено: заменяем контент, а не плюсуем бесконечно к старому
            contentDiv.innerHTML = `<h2>Ваша заявка принята локально:</h2><p>${messageText}</p>`;
            
            // Очищаем форму
            messageInput.value = '';
            messageForm.style.display = 'none';
        }
    </script>
</body>
</html>
