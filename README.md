<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentine's Animation for ASEC Employees</title>
    <style>
        body {
            background-color: #ffccd5;
            overflow: hidden;
            margin: 0;
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
            flex-direction: column;
            position: relative;
        }
        
        /* Background Flowers */
        .background-flower {
            position: absolute;
            font-size: 50px;
            opacity: 0;
            transform: scale(0);
            animation: growFlower 8s linear infinite;
        }

        @keyframes growFlower {
            0% { transform: scale(0); opacity: 0; }
            50% { opacity: 0.8; }
            100% { transform: scale(3); opacity: 0; }
        }

        .heart, .balloon, .flower {
            position: absolute;
            font-size: 24px;
            animation: float 5s linear infinite;
        }
        .heart { color: red; }
        .balloon { color: blue; font-size: 30px; }
        .flower { color: pink; font-size: 28px; }

        @keyframes float {
            0% { transform: translateY(100vh) scale(1); opacity: 1; }
            100% { transform: translateY(-10vh) scale(0.5); opacity: 0; }
        }

        .message-box {
            font-size: 22px;
            font-weight: bold;
            color: #d63384;
            background: rgba(255, 255, 255, 0.6);
            padding: 15px;
            border-radius: 10px;
            margin: 10px 0;
            max-width: 80%;
            position: relative;
            z-index: 2;
        }

        .scroll-text {
            position: fixed;
            bottom: 10px;
            width: 100%;
            white-space: nowrap;
            overflow: hidden;
            font-size: 20px;
            color: #d63384;
            font-weight: bold;
            animation: scrollText 10s linear infinite;
        }

        @keyframes scrollText {
            from { transform: translateX(100%); }
            to { transform: translateX(-100%); }
        }
    </style>
</head>
<body>

    <!-- Background Flowers -->
    <script>
        function createBackgroundFlower() {
            const flower = document.createElement("div");
            flower.innerHTML = "🌺";
            flower.classList.add("background-flower");
            document.body.appendChild(flower);
            
            flower.style.left = Math.random() * 100 + "vw";
            flower.style.top = Math.random() * 100 + "vh";
            flower.style.animationDuration = (Math.random() * 5 + 6) + "s";
            
            setTimeout(() => {
                flower.remove();
            }, 8000);
        }

        setInterval(createBackgroundFlower, 2000);
    </script>

    <div class="message-box">Happy Valentine’s Day to Our Amazing ASEC Team! ❤️💐</div>
    <div class="message-box">On this special day, we want to take a moment to appreciate each and every one of you.</div>
    <div class="message-box">Your dedication, hard work, and passion make ASEC a truly wonderful place to be.</div>
    <div class="message-box">Just like Valentine’s Day is about love and appreciation, we want you to know how much we value and admire your commitment.</div>
    <div class="message-box">May your day be filled with joy, kindness, and sweet moments—whether with family, friends, or colleagues. Thank you for all that you do!</div>
    <div class="message-box">Happy Valentine’s Day! 💖✨</div>

    <div class="scroll-text">From IT Department 💖</div>

    <script>
        function createFloatingElement(emoji, className) {
            const element = document.createElement("div");
            element.innerHTML = emoji;
            element.classList.add(className);
            document.body.appendChild(element);
            
            element.style.left = Math.random() * 100 + "vw";
            element.style.animationDuration = (Math.random() * 2 + 3) + "s";
            
            setTimeout(() => {
                element.remove();
            }, 5000);
        }

        setInterval(() => createFloatingElement("❤️", "heart"), 500);
        setInterval(() => createFloatingElement("🎈", "balloon"), 1000);
        setInterval(() => createFloatingElement("🌸", "flower"), 1200);
    </script>

</body>
</html>
