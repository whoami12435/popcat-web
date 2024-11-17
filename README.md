<!doctype html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Popcat with Counter</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f3f4f6;
            font-family: Arial, sans-serif;
        }

        img {
            width: 300px;
            cursor: pointer;
            transition: transform 0.2s ease;
        }

        img:active {
            transform: scale(0.9);
        }

        .counter {
            margin-top: 20px;
            font-size: 24px;
            font-weight: bold;
        }
    </style>
</head>

<body>
    <img id="popcat" src="https://cdn.prod.website-files.com/5d7e8885cad5174a2fcb98d7/64ad807714d9999c70f0e563_Gawr%2520Gura.jpeg" alt="Popcat">
    <div class="counter">Clicks: <span id="click-count">0</span></div>

    <audio id="meow-sound" src="https://www.myinstants.com/media/sounds/popcat-original.mp3"></audio>

    <script>
        let clickCount = 0; // ตัวแปรเก็บจำนวนคลิก

        const popcat = document.getElementById('popcat');
        const meowSound = document.getElementById('meow-sound');
        const clickCountDisplay = document.getElementById('click-count');

        popcat.addEventListener('mousedown', () => {
            popcat.src = "channels4_profile.jpg"; // เปลี่ยนเป็นแมวอ้าปาก
            meowSound.currentTime = 0; // รีเซ็ตเสียง
            meowSound.play(); // เล่นเสียง
        });

        popcat.addEventListener('mouseup', () => {
            popcat.src = "https://cdn.prod.website-files.com/5d7e8885cad5174a2fcb98d7/64ad807714d9999c70f0e563_Gawr%2520Gura.jpeg"; // กลับเป็นแมวปิดปาก
            clickCount++; // เพิ่มจำนวนคลิก
            clickCountDisplay.textContent = clickCount; // อัปเดตจำนวนคลิกในหน้าเว็บ
        });
    </script>
</body>

</html>
