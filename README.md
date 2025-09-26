<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animated Profile - Your Name</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            text-align: center;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 20px;
            padding: 50px;
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
            animation: containerFloat 6s ease-in-out infinite;
        }

        @keyframes containerFloat {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .name {
            font-size: 4em;
            font-weight: bold;
            color: #fff;
            margin-bottom: 20px;
            animation: nameGlow 3s ease-in-out infinite alternate;
            text-shadow: 0 0 20px rgba(255, 255, 255, 0.8);
        }

        @keyframes nameGlow {
            from {
                text-shadow: 0 0 20px rgba(255, 255, 255, 0.8),
                            0 0 30px rgba(255, 255, 255, 0.6),
                            0 0 40px rgba(255, 255, 255, 0.4);
            }
            to {
                text-shadow: 0 0 30px rgba(255, 255, 255, 1),
                            0 0 40px rgba(255, 255, 255, 0.8),
                            0 0 50px rgba(255, 255, 255, 0.6);
            }
        }

        .roll-number {
            font-size: 2em;
            color: #fff;
            margin-bottom: 30px;
            animation: rollSlide 2s ease-in-out infinite;
            opacity: 0.9;
        }

        @keyframes rollSlide {
            0%, 100% { transform: translateX(0px); }
            25% { transform: translateX(-10px); }
            75% { transform: translateX(10px); }
        }

        .animated-text {
            font-size: 1.5em;
            color: #fff;
            margin: 20px 0;
            animation: textBounce 4s ease-in-out infinite;
        }

        @keyframes textBounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            animation: twinkle 2s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0; transform: scale(0); }
            50% { opacity: 1; transform: scale(1); }
        }

        .floating-shapes {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .shape {
            position: absolute;
            opacity: 0.3;
            animation: floatShapes 20s linear infinite;
        }

        .circle {
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.2);
        }

        .square {
            background: rgba(255, 255, 255, 0.15);
            transform: rotate(45deg);
        }

        @keyframes floatShapes {
            0% {
                transform: translateY(100vh) rotate(0deg);
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
            }
        }

        .profile-info {
            margin-top: 30px;
            animation: fadeInUp 2s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .social-links {
            margin-top: 30px;
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        .social-link {
            width: 50px;
            height: 50px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            font-size: 1.2em;
            transition: all 0.3s ease;
            animation: socialPulse 3s ease-in-out infinite;
        }

        @keyframes socialPulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .social-link:hover {
            background: rgba(255, 255, 255, 0.4);
            transform: scale(1.2) !important;
        }

        /* Responsive design */
        @media (max-width: 768px) {
            .container {
                padding: 30px 20px;
                margin: 20px;
            }
            
            .name {
                font-size: 2.5em;
            }
            
            .roll-number {
                font-size: 1.5em;
            }
            
            .animated-text {
                font-size: 1.2em;
            }
        }
    </style>
</head>
<body>
    <div class="stars" id="stars"></div>
    
    <div class="floating-shapes" id="floating-shapes"></div>
    
    <div class="container">
        <h1 class="name" id="studentName">Tahir Attar</h1>
        <h2 class="roll-number" id="rollNumber">Roll Number: 4162</h2>
        
        <div class="profile-info">
            <p class="animated-text">✨ Student Profile ✨</p>
            <p class="animated-text">Welcome to my animated webpage!</p>
        </div>
        
        <div class="social-links">
            <a href="#" class="social-link" title="Email">📧</a>
            <a href="#" class="social-link" title="LinkedIn">💼</a>
            <a href="#" class="social-link" title="GitHub">🔗</a>
            <a href="#" class="social-link" title="Portfolio">🌐</a>
        </div>
    </div>

    <script>
        // Create animated stars
        function createStars() {
            const starsContainer = document.getElementById('stars');
            const numberOfStars = 50;
            
            for (let i = 0; i < numberOfStars; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.width = Math.random() * 3 + 1 + 'px';
                star.style.height = star.style.width;
                star.style.animationDelay = Math.random() * 2 + 's';
                starsContainer.appendChild(star);
            }
        }
        
        // Create floating shapes
        function createFloatingShapes() {
            const shapesContainer = document.getElementById('floating-shapes');
            const numberOfShapes = 15;
            
            for (let i = 0; i < numberOfShapes; i++) {
                const shape = document.createElement('div');
                const isCircle = Math.random() > 0.5;
                
                shape.className = `shape ${isCircle ? 'circle' : 'square'}`;
                shape.style.left = Math.random() * 100 + '%';
                shape.style.width = Math.random() * 20 + 10 + 'px';
                shape.style.height = shape.style.width;
                shape.style.animationDelay = Math.random() * 20 + 's';
                shape.style.animationDuration = (Math.random() * 10 + 15) + 's';
                
                shapesContainer.appendChild(shape);
            }
        }
        
        // Typewriter effect for name
        function typeWriter(element, text, speed = 100) {
            let i = 0;
            element.innerHTML = '';
            
            function type() {
                if (i < text.length) {
                    element.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                }
            }
            type();
        }
        
        // Interactive features
        document.addEventListener('DOMContentLoaded', function() {
            createStars();
            createFloatingShapes();
            
            // Add click effect to container
            const container = document.querySelector('.container');
            container.addEventListener('click', function() {
                this.style.transform = 'scale(1.05)';
                setTimeout(() => {
                    this.style.transform = 'scale(1)';
                }, 200);
            });
            
            // Add mouse move effect
            document.addEventListener('mousemove', function(e) {
                const container = document.querySelector('.container');
                const rect = container.getBoundingClientRect();
                const centerX = rect.left + rect.width / 2;
                const centerY = rect.top + rect.height / 2;
                
                const deltaX = (e.clientX - centerX) * 0.01;
                const deltaY = (e.clientY - centerY) * 0.01;
                
                container.style.transform = `translate(${deltaX}px, ${deltaY}px)`;
            });
        });
        
        // Function to update name and roll number
        function updateProfile(name, rollNumber) {
            document.getElementById('studentName').textContent = name;
            document.getElementById('rollNumber').textContent = `Roll Number: ${rollNumber}`;
        }
        
        // Example usage - replace with your actual name and roll number
        // updateProfile("John Doe", "CS2023001");
    </script>
</body>
</html>
