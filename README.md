<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exploding Hearts</title>
    <style>
        body {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }

        .heart-container {
            text-align: center;
            margin: 10px;
            display: inline-block;
        }

        .heart {
            font-size: 50px;
            cursor: pointer;
            transition: transform 0.5s ease-out;
        }

        .red { color: red; }
        .blue { color: blue; }
        .green { color: green; }
        .purple { color: purple; }
    </style>
</head>
<body>

    <div class="heart-container">
        <div class="heart red" onclick="explodeHeart('red')">❤️</div>
        <p class="message">Click the red heart!</p>
    </div>

    <div class="heart-container">
        <div class="heart blue" onclick="explodeHeart('blue')">❤️</div>
        <p class="message">Click my blue heart!</p>
    </div>

    <div class="heart-container">
        <div class="heart green" onclick="explodeHeart('green')">❤️</div>
        <p class="message">Click my green heart!</p>
    </div>

    <div class="heart-container">
        <div class="heart purple" onclick="explodeHeart('purple')">❤️</div>
        <p class="message">Click my purple heart!</p>
    </div>
    
    <script>
        function explodeHeart(color) {
            var heart = document.querySelector(`.${color}`);
            var message = document.querySelector(`.${color} + .message`);
            
            // Update message
            message.innerHTML = `I love you with ${color} heart!`;

            // Explode effect
            heart.style.transform = 'scale(3)';
            setTimeout(function() {
                heart.style.transform = 'scale(1)';
                // Reset message after the explosion
                message.innerHTML = `Click the ${color} heart!`;
            }, 500);
        }
    </script>

</body>
</html>
