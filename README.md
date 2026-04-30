<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ZERO-X // Core Profile</title>
    <style>
        :root {
            --bg-color: #050505;
            --text-color: #ffffff;
            --border-color: #333333;
            --accent-color: #aaaaaa;
            --font-family: 'Courier New', Courier, monospace;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            font-family: var(--font-family);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            perspective: 1000px;
            overflow: hidden;
        }

        .card {
            background: #000000;
            border: 1px solid var(--border-color);
            padding: 40px;
            width: 800px;
            max-width: 90%;
            box-shadow: 0 0 40px rgba(255, 255, 255, 0.05);
            border-radius: 4px;
            transform-style: preserve-3d;
            animation: float 6s ease-in-out infinite alternate;
        }

        @keyframes float {
            0% {
                transform: translateY(0px) rotateX(2deg) rotateY(-2deg);
            }
            100% {
                transform: translateY(-10px) rotateX(-2deg) rotateY(2deg);
            }
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
        }

        .header h1 {
            font-size: 2.5rem;
            letter-spacing: 5px;
            font-weight: 300;
            margin-bottom: 10px;
            text-transform: uppercase;
        }

        .header p {
            color: var(--accent-color);
            font-size: 0.9rem;
            letter-spacing: 2px;
        }

        .terminal {
            border-top: 1px solid var(--border-color);
            border-bottom: 1px solid var(--border-color);
            padding: 20px 0;
            margin-bottom: 40px;
            display: flex;
            flex-direction: column;
            gap: 10px;
            font-size: 0.95rem;
        }

        .terminal-line {
            display: flex;
            align-items: center;
        }

        .prompt {
            color: var(--accent-color);
            margin-right: 10px;
        }

        .command {
            animation: typing 2s steps(40, end) infinite;
            overflow: hidden;
            white-space: nowrap;
            width: 100%;
            border-right: 1px solid #fff;
        }

        @keyframes typing {
            0% { width: 0; }
            50% { width: 100%; }
            100% { width: 100%; }
        }

        .section-title {
            font-size: 0.9rem;
            letter-spacing: 2px;
            margin-bottom: 20px;
            color: var(--accent-color);
            text-transform: uppercase;
        }

        .skills {
            display: flex;
            gap: 15px;
            margin-bottom: 40px;
            flex-wrap: wrap;
        }

        .badge {
            border: 1px solid var(--border-color);
            padding: 8px 16px;
            font-size: 0.8rem;
            letter-spacing: 1px;
            transition: all 0.3s ease;
            background: #000;
            color: #fff;
            text-decoration: none;
        }

        .badge:hover {
            background: #fff;
            color: #000;
        }

        .footer {
            text-align: center;
            font-size: 0.8rem;
            color: var(--accent-color);
            border-top: 1px solid var(--border-color);
            padding-top: 20px;
        }

        .footer a {
            color: #fff;
            text-decoration: none;
            border-bottom: 1px dotted #fff;
        }
    </style>
</head>
<body>
    <div class="card">
        <div class="header">
            <h1>ZERO-X</h1>
            <p>// The Core Profile</p>
        </div>
        
        <div class="terminal">
            <div class="terminal-line">
                <span class="prompt">root@zero-x:~#</span>
                <span class="command">./init_profile.sh</span>
            </div>
            <div class="terminal-line">
                <span class="prompt">[INFO]</span>
                <span>System online. Architecting minimal software structures.</span>
            </div>
        </div>

        <div class="section-title">// Skill Matrix</div>
        <div class="skills">
            <span class="badge">RUST</span>
            <span class="badge">TYPESCRIPT</span>
            <span class="badge">WEBGL</span>
            <span class="badge">THREE.JS</span>
            <span class="badge">LINUX</span>
        </div>

        <div class="footer">
            <p>Designed with minimalism in mind. <a href="https://github.com" target="_blank">GitHub</a></p>
        </div>
    </div>
</body>
</html>
