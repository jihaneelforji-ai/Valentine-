https://Jihane.github.io/valentine/
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine? 💝</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&family=Poppins:wght@300;400;600&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-red: #ff1744;
            --deep-rose: #c2185b;
            --soft-pink: #f8bbd0;
            --blush: #fce4ec;
            --gold: #ffd700;
            --white: #ffffff;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 50%, #fecfef 100%);
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        /* Floating Hearts Background */
        .hearts-container {
            position: fixed;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 0;
            pointer-events: none;
        }

        .heart {
            position: absolute;
            font-size: 20px;
            color: rgba(255, 23, 68, 0.3);
            animation: float 6s ease-in infinite;
            bottom: -100px;
        }

        @keyframes float {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 0.8;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Main Container */
        .container {
            position: relative;
            z-index: 1;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }

        /* Question Section */
        .question-section {
            text-align: center;
            background: rgba(255, 255, 255, 0.95);
            padding: 60px 40px;
            border-radius: 30px;
            box-shadow: 0 20px 60px rgba(255, 23, 68, 0.2);
            animation: fadeIn 1s ease-out;
            max-width: 600px;
            width: 90%;
            backdrop-filter: blur(10px);
            border: 2px solid rgba(255, 255, 255, 0.5);
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .valentine-title {
            font-family: 'Dancing Script', cursive;
            font-size: 3.5rem;
            color: var(--primary-red);
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }

        .valentine-question {
            font-size: 1.5rem;
            color: var(--deep-rose);
            margin-bottom: 40px;
            font-weight: 300;
        }

        .buttons {
            display: flex;
            gap: 30px;
            justify-content: center;
            flex-wrap: wrap;
            position: relative;
        }

        .btn {
            padding: 15px 40px;
            font-size: 1.2rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: 'Poppins', sans-serif;
            font-weight: 600;
            position: relative;
            overflow: hidden;
        }

        .btn-yes {
            background: linear-gradient(135deg, #ff1744 0%, #ff5722 100%);
            color: white;
            box-shadow: 0 10px 30px rgba(255, 23, 68, 0.3);
        }

        .btn-yes:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 15px 40px rgba(255, 23, 68, 0.4);
        }

        .btn-no {
            background: #e0e0e0;
            color: #666;
            position: relative;
            transition: all 0.3s ease;
        }

        /* Gifts Section (Hidden initially) */
        .gifts-section {
            display: none;
            width: 100%;
            max-width: 1000px;
            animation: fadeIn 1s ease-out;
        }

        .gifts-header {
            text-align: center;
            margin-bottom: 40px;
            color: white;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }

        .gifts-header h2 {
            font-family: 'Dancing Script', cursive;
            font-size: 3rem;
            margin-bottom: 10px;
        }

        .gifts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            padding: 20px;
        }

        .gift-card {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            border: 2px solid transparent;
        }

        .gift-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
            transition: left 0.5s;
        }

        .gift-card:hover::before {
            left: 100%;
        }

        .gift-card:hover {
            transform: translateY(-10px) rotate(2deg);
            box-shadow: 0 20px 40px rgba(255, 23, 68, 0.2);
            border-color: var(--soft-pink);
        }

        .gift-icon {
            font-size: 3.5rem;
            margin-bottom: 15px;
            display: block;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .gift-title {
            font-family: 'Dancing Script', cursive;
            font-size: 1.8rem;
            color: var(--primary-red);
            margin-bottom: 10px;
        }

        .gift-desc {
            color: #666;
            font-size: 0.95rem;
            line-height: 1.4;
        }

        .redeem-btn {
            margin-top: 15px;
            padding: 8px 20px;
            background: var(--soft-pink);
            color: var(--deep-rose);
            border: none;
            border-radius: 20px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }

        .redeem-btn:hover {
            background: var(--primary-red);
            color: white;
        }

        /* Modal for gift details */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.6);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            backdrop-filter: blur(5px);
        }

        .modal-content {
            background: white;
            padding: 40px;
            border-radius: 20px;
            max-width: 500px;
            text-align: center;
            animation: popIn 0.3s ease-out;
            position: relative;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
        }

        @keyframes popIn {
            from { transform: scale(0.8); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        .close-modal {
            position: absolute;
            top: 15px;
            right: 20px;
            font-size: 2rem;
            cursor: pointer;
            color: #999;
            transition: color 0.3s;
        }

        .close-modal:hover {
            color: var(--primary-red);
        }

        .modal-icon {
            font-size: 4rem;
            margin-bottom: 20px;
        }

        .modal h3 {
            font-family: 'Dancing Script', cursive;
            font-size: 2rem;
            color: var(--primary-red);
            margin-bottom: 15px;
        }

        .modal p {
            color: #555;
            line-height: 1.6;
            font-size: 1.1rem;
        }

        /* Confetti */
        .confetti {
            position: fixed;
            width: 10px;
            height: 10px;
            background: #f00;
            position: absolute;
            animation: confetti-fall 3s linear forwards;
            z-index: 999;
        }

        @keyframes confetti-fall {
            to {
                transform: translateY(100vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Responsive */
        @media (max-width: 600px) {
            .valentine-title { font-size: 2.5rem; }
            .gifts-header h2 { font-size: 2rem; }
            .gifts-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <!-- Floating Hearts Background -->
    <div class="hearts-container" id="heartsContainer"></div>

    <div class="container">
        <!-- Question Section -->
        <div class="question-section" id="questionSection">
            <h1 class="valentine-title">Happy Valentine's Day! 💘</h1>
            <p class="valentine-question">Will you be my Valentine?</p>
            <div class="buttons">
                <button class="btn btn-yes" onclick="sayYes()">Yes, absolutely! 💖</button>
                <button class="btn btn-no" id="noBtn" onmouseover="moveNo()" onclick="moveNo()">No 💔</button>
            </div>
        </div>

        <!-- Gifts Section (Hidden) -->
        <div class="gifts-section" id="giftsSection">
            <div class="gifts-header">
                <h2>You've unlocked my heart! 🎁</h2>
                <p>Choose your gifts, my love...</p>
            </div>
            
            <div class="gifts-grid">
                <!-- Gift 1: Flowers -->
                <div class="gift-card" onclick="openGift(0)">
                    <span class="gift-icon">🌹</span>
                    <h3 class="gift-title">Beautiful Flowers</h3>
                    <p class="gift-desc">A bouquet of red roses as beautiful as your smile</p>
                    <button class="redeem-btn">Claim Gift</button>
                </div>

                <!-- Gift 2: Chocolate -->
                <div class="gift-card" onclick="openGift(1)">
                    <span class="gift-icon">🍫</span>
                    <h3 class="gift-title">Sweet Chocolate</h3>
                    <p class="gift-desc">Sweeter than honey, just like our love</p>
                    <button class="redeem-btn">Claim Gift</button>
                </div>

                <!-- Gift 3: Hug -->
                <div class="gift-card" onclick="openGift(2)">
                    <span class="gift-icon">🤗</span>
                    <h3 class="gift-title">Warm Hug</h3>
                    <p class="gift-desc">A tight hug that lasts forever</p>
                    <button class="redeem-btn">Claim Gift</button>
                </div>

                <!-- Gift 4: Kiss -->
                <div class="gift-card" onclick="openGift(3)">
                    <span class="gift-icon">💋</span>
                    <h3 class="gift-title">Tender Kiss</h3>
                    <p class="gift-desc">Sealed with a kiss and infinite love</p>
                    <button class="redeem-btn">Claim Gift</button>
                </div>

                <!-- Gift 5: Date -->
                <div class="gift-card" onclick="openGift(4)">
                    <span class="gift-icon">🥂</span>
                    <h3 class="gift-title">Romantic Date</h3>
                    <p class="gift-desc">Dinner under the stars, just you and me</p>
                    <button class="redeem-btn">Claim Gift</button>
                </div>

                <!-- Gift 6: Message -->
                <div class="gift-card" onclick="openGift(5)">
                    <span class="gift-icon">💌</span>
                    <h3 class="gift-title">Love Message</h3>
                    <p class="gift-desc">Words from my heart to yours</p>
                    <button class="redeem-btn">Claim Gift</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Modal -->
    <div class="modal" id="modal" onclick="closeModal(event)">
        <div class="modal-content" onclick="event.stopPropagation()">
            <span class="close-modal" onclick="closeModal()">&times;</span>
            <div class="modal-icon" id="modalIcon">🎁</div>
            <h3 id="modalTitle">Gift Title</h3>
            <p id="modalText">Gift description goes here...</p>
        </div>
    </div>

    <script>
        // Create floating hearts
        function createHearts() {
            const container = document.getElementById('heartsContainer');
            const heartSymbols = ['💕', '💖', '💗', '💓', '💝', '🌸', '✨'];
            
            setInterval(() => {
                const heart = document.createElement('div');
                heart.className = 'heart';
                heart.textContent = heartSymbols[Math.floor(Math.random() * heartSymbols.length)];
                heart.style.left = Math.random() * 100 + '%';
                heart.style.animationDuration = (Math.random() * 3 + 4) + 's';
                heart.style.fontSize = (Math.random() * 20 + 15) + 'px';
                container.appendChild(heart);
                
                setTimeout(() => heart.remove(), 7000);
            }, 300);
        }

        createHearts();

        // Gift data
        const gifts = [
            {
                icon: '🌹',
                title: 'Beautiful Flowers',
                message: 'Like these roses, my love for you is eternal and beautiful. Each petal represents a reason why I adore you. You deserve a garden of happiness! 🌹❤️'
            },
            {
                icon: '🍫',
                title: 'Sweet Chocolate',
                message: 'Life is like a box of chocolates, but you\'re the sweetest piece of all! I promise to make every moment with you as delightful as cocoa. 🍫💕'
            },
            {
                icon: '🤗',
                title: 'Warm Hug',
                message: 'Here\'s a virtual hug that\'s tight, warm, and full of love. In reality, I\'m saving the biggest, cosiest hug just for you. Can\'t wait to hold you! 🤗💖'
            },
            {
                icon: '💋',
                title: 'Tender Kiss',
                message: 'A kiss to seal our love story. Soft as a feather, warm as the sun, and filled with all the passion my heart holds for you. 💋😘'
            },
            {
                icon: '🥂',
                title: 'Romantic Date',
                message: 'I\'m taking you out! Dress up pretty (though you always look stunning). Dinner, candles, soft music, and my eyes only on you. Date night is on me! 🌟🍷'
            },
            {
                icon: '💌',
                title: 'Love Message',
                message: 'You are my first thought in the morning and my last thought at night. In this crazy world, you are my peace, my joy, and my forever Valentine. I love you! 💌❤️'
            }
        ];

        // Move No button randomly (playful)
        function moveNo() {
            const btn = document.getElementById('noBtn');
            const x = Math.random() * (window.innerWidth - 200);
            const y = Math.random() * (window.innerHeight - 100);
            btn.style.position = 'fixed';
            btn.style.left = x + 'px';
            btn.style.top = y + 'px';
            btn.style.transition = 'all 0.3s ease';
        }

        // Say Yes function
        function sayYes() {
            // Confetti explosion
            createConfetti();
            
            // Transition
            setTimeout(() => {
                document.getElementById('questionSection').style.display = 'none';
                document.getElementById('giftsSection').style.display = 'block';
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }, 500);
        }

        // Create confetti
        function createConfetti() {
            const colors = ['#ff1744', '#ff5722', '#ffd700', '#e91e63', '#f06292'];
            for (let i = 0; i < 50; i++) {
                setTimeout(() => {
                    const confetti = document.createElement('div');
                    confetti.className = 'confetti';
                    confetti.style.left = Math.random() * 100 + 'vw';
                    confetti.style.background = colors[Math.floor(Math.random() * colors.length)];
                    confetti.style.borderRadius = Math.random() > 0.5 ? '50%' : '0';
                    confetti.style.animationDuration = (Math.random() * 2 + 2) + 's';
                    document.body.appendChild(confetti);
                    setTimeout(() => confetti.remove(), 4000);
                }, i * 30);
            }
        }

        // Open gift modal
        function openGift(index) {
            const gift = gifts[index];
            document.getElementById('modalIcon').textContent = gift.icon;
            document.getElementById('modalTitle').textContent = gift.title;
            document.getElementById('modalText').textContent = gift.message;
            document.getElementById('modal').style.display = 'flex';
        }

        // Close modal
        function closeModal(event) {
            if (!event || event.target.id === 'modal') {
                document.getElementById('modal').style.display = 'none';
            }
        }

        // Prevent closing on content click
        document.querySelector('.modal-content').addEventListener('click', (e) => {
            e.stopPropagation();
        });
    </script>
</body>
</html>
