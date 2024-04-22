<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TheOM4R</title>
    <style>
        body {
            background-color: black;
            color: white;
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            overflow: hidden;
        }
        #container {
            position: relative;
            width: 100%;
            height: 100vh;
        }
        #content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            z-index: 1;
        }
        #background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
        }
        a {
            color: white;
            text-decoration: none;
            transition: color 0.3s ease, text-shadow 0.3s ease; /* Added transition for text-shadow */
        }
        a:hover {
            color: cyan; /* Change the glow color on hover */
            text-shadow: 0 0 10px cyan, 0 0 20px cyan, 0 0 40px cyan, 0 0 80px cyan, 0 0 120px cyan; /* Increased glow effect */
        }
    </style>
</head>
<body>
    <div id="container">
        <div id="content">
            <h1>Welcome to TheOM4R</h1>
            <p>Explore my online presence:</p>
            <ul>
                <li><a href="https://www.youtube.com/@the_om4r" target="_blank">YouTube Channel</a></li>
                <li><a href="https://www.twitch.tv/ridlyzegd" target="_blank">Twitch Profile</a></li>
                <li><a href="https://twitter.com/ridlyze" target="_blank">Twitter Account</a></li>
                <li><a href="https://discord.gg/W5x4XnsJTB" target="_blank">Discord Server</a></li>
            </ul>
        </div>
        <canvas id="background"></canvas>
    </div>

    <!-- Script for creating the moving background -->
    <script>
        const canvas = document.getElementById('background');
        const ctx = canvas.getContext('2d');

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        let lines = [];
        const numLines = 50;

        for (let i = 0; i < numLines; i++) {
            lines.push({
                x: Math.random() * canvas.width,
                y: Math.random() * canvas.height,
                length: Math.random() * 100 + 50,
                angle: Math.random() * Math.PI * 2,
                thickness: Math.random() * 2 + 1,
                opacity: Math.random() * 0.5 + 0.5
            });
        }

        function draw() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            lines.forEach(line => {
                ctx.beginPath();
                ctx.moveTo(line.x, line.y);
                ctx.lineTo(line.x + Math.cos(line.angle) * line.length, line.y + Math.sin(line.angle) * line.length);
                ctx.strokeStyle = `rgba(255, 255, 255, ${line.opacity})`;
                ctx.lineWidth = line.thickness;
                ctx.stroke();
            });
        }

        function update() {
            lines.forEach(line => {
                line.x += Math.cos(line.angle) * 2;
                line.y += Math.sin(line.angle) * 2;

                if (line.x < 0 || line.x > canvas.width || line.y < 0 || line.y > canvas.height) {
                    line.x = Math.random() * canvas.width;
                    line.y = Math.random() * canvas.height;
                }
            });
        }

        function loop() {
            update();
            draw();
            requestAnimationFrame(loop);
        }

        loop();
    </script>
</body>
</html>
