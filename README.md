<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>𝕯𝖔𝖇𝖗𝖔 - Online</title>
    <!-- Подключаем стильный шрифт Montserrat -->
    <link rel="preconnect" href="https://googleapis.com">
    <link rel="preconnect" href="https://gstatic.com" crossorigin>
    <link href="https://googleapis.com/css2?family=Montserrat:wght@300;400;600;700;900&display=swap" rel="stylesheet">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Montserrat', sans-serif;
        }

        body {
            background-color: #060409;
            color: #ffffff;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 40px 20px;
            position: relative;
            overflow: hidden;
        }

        /* Премиальный живой анимированный фон */
        .neon-bg {
            position: absolute;
            top: -50%;
            left: -50%;
            right: -50%;
            bottom: -50%;
            width: 200%;
            height: 200vh;
            background: radial-gradient(circle at 30% 30%, #240046 0%, transparent 40%),
                        radial-gradient(circle at 70% 60%, #3c096c 0%, transparent 45%),
                        radial-gradient(circle at 50% 20%, #7b2cbf 0%, transparent 35%);
            opacity: 0.6;
            filter: blur(80px);
            z-index: 0;
            animation: fluidMovement 25s infinite alternate ease-in-out;
            pointer-events: none;
        }

        .neon-bg::after {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255, 0, 127, 0.15) 0%, transparent 50%, rgba(0, 242, 254, 0.1) 100%);
            animation: rotateBg 35s infinite linear;
        }

        @keyframes fluidMovement {
            0% { transform: translate(0, 0) scale(1); }
            50% { transform: translate(5%, -5%) scale(1.1); }
            100% { transform: translate(-3%, 4%) scale(0.95); }
        }

        @keyframes rotateBg {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Огромная красивая надпись сверху сайта */
        .header-title {
            z-index: 2;
            text-align: center;
            max-width: 600px;
            margin-bottom: 35px;
            padding: 0 10px;
            animation: fadeInDown 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }

        .header-title h1 {
            font-size: 28px;
            font-weight: 900;
            letter-spacing: 1.5px;
            line-height: 1.3;
            text-transform: uppercase;
            background: linear-gradient(135deg, #ffffff 20%, #c77dff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 10px 30px rgba(199, 125, 255, 0.2);
        }

        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-25px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Главная Glassmorphism-карточка визитки */
        .card {
            background: rgba(14, 8, 24, 0.55);
            backdrop-filter: blur(35px);
            -webkit-backdrop-filter: blur(35px);
            border: 1px solid rgba(157, 78, 221, 0.25);
            border-radius: 28px;
            padding: 45px 35px;
            width: 100%;
            max-width: 410px;
            text-align: center;
            box-shadow: 0 40px 80px rgba(0, 0, 0, 0.8), 
                        0 0 50px rgba(123, 44, 191, 0.15);
            z-index: 2;
            position: relative;
            transform: translateY(20px);
            opacity: 0;
            animation: cardAppear 0.8s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
        }

        @keyframes cardAppear {
            to { transform: translateY(0); opacity: 1; }
        }

        /* Сияющая плашка статуса */
        .status-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: rgba(157, 78, 221, 0.08);
            border: 1px solid rgba(157, 78, 221, 0.5);
            padding: 9px 24px;
            border-radius: 50px;
            font-size: 11px;
            font-weight: 700;
            letter-spacing: 2.5px;
            color: #d8bbff;
            text-transform: uppercase;
            margin-bottom: 35px;
            box-shadow: 0 0 20px rgba(157, 78, 221, 0.2);
            animation: pulseGlow 2.5s infinite alternate ease-in-out;
        }

        /* Пульсирующая точка статуса */
        .status-badge::before {
            content: '';
            display: inline-block;
            width: 6px;
            height: 6px;
            background-color: #00f5d4;
            border-radius: 50%;
            box-shadow: 0 0 10px #00f5d4;
        }

        @keyframes pulseGlow {
            0% { transform: scale(1); box-shadow: 0 0 15px rgba(157, 78, 221, 0.2); border-color: rgba(157, 78, 221, 0.4); }
            100% { transform: scale(1.03); box-shadow: 0 0 30px rgba(157, 78, 221, 0.5); border-color: #c77dff; }
        }

        /* Крупный неоновый готический никнейм без авы */
        .nickname {
            font-size: 42px;
            font-weight: 800;
            margin-bottom: 35px;
            letter-spacing: 1.5px;
            background: linear-gradient(135deg, #ffffff 30%, #e0aaff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 10px 20px rgba(0,0,0,0.3);
        }

        /* Кнопка скопировать юзернейм */
        .btn-copy {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: linear-gradient(135deg, rgba(121, 40, 202, 0.2), rgba(255, 0, 127, 0.04));
            border: 1px solid rgba(121, 40, 202, 0.4);
            padding: 22px 26px;
            border-radius: 18px;
            color: #ffffff;
            font-size: 15px;
            font-weight: 600;
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
            cursor: pointer;
        }

        .btn-copy:hover {
            background: linear-gradient(135deg, rgba(121, 40, 202, 0.35), rgba(255, 0, 127, 0.08));
            border-color: #ff007f;
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(255, 0, 127, 0.25);
        }

        .btn-copy .icon-copy {
            color: #ff007f;
            font-size: 13px;
            background: rgba(255, 0, 127, 0.12);
            padding: 7px 14px;
            border-radius: 9px;
            font-weight: 700;
            letter-spacing: 0.5px;
            transition: all 0.3s ease;
        }

        .btn-copy:hover .icon-copy {
            background: #ff007f;
            color: #fff;
        }

        /* Кастомный всплывающий Toast */
        .toast {
            position: fixed;
            bottom: -70px;
            left: 50%;
            transform: translateX(-50%);
            background: rgba(255, 0, 127, 0.9);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            color: white;
            padding: 14px 28px;
            border-radius: 50px;
            font-size: 14px;
            font-weight: 700;
            box-shadow: 0 15px 30px rgba(255, 0, 127, 0.4);
            transition: bottom 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            z-index: 10;
            letter-spacing: 0.5px;
        }

        .toast.show {
            bottom: 45px;
        }
    </style>
</head>
<body>

    <!-- Живой ликвидный фон -->
    <div class="neon-bg"></div>

    <!-- Большая надпись красивым шрифтом сверху сайта -->
    <div class="header-title">
        <h1>Скопируй юз и вставь в поиск телеграмма</h1>
    </div>

    <!-- Главная Glassmorphism-карточка визитки -->
    <div class="card">
        <!-- Современное окно с надписью Online -->
        <div class="status-badge">Online 10:00 - 23:00 мск</div>

        <!-- Крупный готический ник без аватарки -->
        <div class="nickname">𝕯𝖔𝖇𝖗𝖔</div>

        <!-- Один единственный пункт: Скопировать юзернейм -->
        <div class="btn-link btn-copy" onclick="copyUsername()">
            <span>Скопировать юзернейм @DobroX0</span>
            <span class="icon-copy" id="copy-text">COPY</span>
        </div>
    </div>

    <!-- Всплывающий Тост (Уведомление) -->
    <div class="toast" id="toast">Юзернейм скопирован!</div>

    <!-- Скрипт для копирования и анимации кнопки -->
    <script>
        function copyUsername() {
            const username = "@DobroX0";
            
            navigator.clipboard.writeText(username).then(() => {
                const toast = document.getElementById("toast");
                const copyText = document.getElementById("copy-text");
                
                copyText.innerText = "COPIED!";
                toast.classList.add("show");
                
                setTimeout(() => {
                    toast.classList.remove("show");
                    copyText.innerText = "COPY";
                }, 2500);
            }).catch(err => {
                console.error("Не удалось скопировать: ", err);
            });
        }
    </script>
</body>
</html>
