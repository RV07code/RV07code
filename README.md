<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ZERO-X // 3D Core Profile</title>
    <style>
        :root {
            --bg-color: #030303;
            --text-color: #ffffff;
            --accent-color: #999999;
            --border-color: #222222;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body, html {
            width: 100%;
            height: 100%;
            overflow: hidden;
            background-color: var(--bg-color);
            font-family: 'Courier New', Courier, monospace;
            color: var(--text-color);
        }

        #canvas3d {
            position: absolute;
            top: 0;
            left: 0;
            z-index: 1;
        }

        .container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 2;
            width: 80vw;
            max-width: 600px;
            background: rgba(0, 0, 0, 0.75);
            border: 1px solid var(--border-color);
            padding: 40px;
            box-shadow: 0 0 60px rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(8px);
            -webkit-backdrop-filter: blur(8px);
            border-radius: 6px;
        }

        .header {
            text-align: center;
            margin-bottom: 30px;
        }

        .header h1 {
            font-size: 2.5rem;
            letter-spacing: 6px;
            font-weight: 300;
            margin-bottom: 8px;
            text-transform: uppercase;
        }

        .header p {
            font-size: 0.9rem;
            color: var(--accent-color);
            letter-spacing: 3px;
        }

        .content {
            border-top: 1px solid var(--border-color);
            border-bottom: 1px solid var(--border-color);
            padding: 25px 0;
            margin-bottom: 30px;
            line-height: 1.8;
            font-size: 0.95rem;
        }

        .content-line {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }

        .content-line span:first-child {
            color: var(--accent-color);
        }

        .skills {
            display: flex;
            justify-content: center;
            gap: 12px;
            flex-wrap: wrap;
            margin-bottom: 30px;
        }

        .badge {
            font-size: 0.75rem;
            padding: 6px 12px;
            border: 1px solid var(--border-color);
            color: var(--text-color);
            background: rgba(255, 255, 255, 0.05);
            text-decoration: none;
            letter-spacing: 2px;
            transition: all 0.3s ease;
        }

        .badge:hover {
            background: #ffffff;
            color: #000000;
        }

        .footer {
            text-align: center;
            font-size: 0.8rem;
            color: var(--accent-color);
        }

        .footer a {
            color: var(--text-color);
            text-decoration: none;
            border-bottom: 1px dotted var(--text-color);
        }
    </style>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
</head>
<body>
    <canvas id="canvas3d"></canvas>
    
    <div class="container">
        <div class="header">
            <h1>ZERO-X</h1>
            <p>// Core Profile Architecture</p>
        </div>
        
        <div class="content">
            <div class="content-line">
                <span>SYSTEM</span>
                <span>ONLINE</span>
            </div>
            <div class="content-line">
                <span>ROLE</span>
                <span>ARCHITECT / GRAPHICS ENGINEER</span>
            </div>
            <div class="content-line">
                <span>STATUS</span>
                <span>COMPUTING 3D STRUCTURES</span>
            </div>
        </div>

        <div class="skills">
            <a href="#" class="badge">RUST</a>
            <a href="#" class="badge">WEBGL</a>
            <a href="#" class="badge">THREE.JS</a>
            <a href="#" class="badge">TYPESCRIPT</a>
        </div>

        <div class="footer">
            <p>Designed with minimalism in mind. <a href="https://github.com" target="_blank">GITHUB</a></p>
        </div>
    </div>

    <script>
        // 3D Background with Three.js
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const renderer = new THREE.WebGLRenderer({ canvas: document.getElementById('canvas3d'), alpha: true });
        
        renderer.setSize(window.innerWidth, window.innerHeight);
        renderer.setPixelRatio(window.devicePixelRatio);

        // Create stars/particles
        const geometry = new THREE.BufferGeometry();
        const count = 1500;
        const positions = new Float32Array(count * 3);

        for(let i = 0; i < count * 3; i++) {
            positions[i] = (Math.random() - 0.5) * 10;
        }

        geometry.setAttribute('position', new THREE.BufferAttribute(positions, 3));

        const material = new THREE.PointsMaterial({
            color: 0xffffff,
            size: 0.02,
            transparent: true,
            opacity: 0.5
        });

        const particles = new THREE.Points(geometry, material);
        scene.add(particles);

        // Add some glowing wireframe shapes (3D element)
        const geometry2 = new THREE.IcosahedronGeometry(2, 1);
        const material2 = new THREE.MeshBasicMaterial({
            color: 0xffffff,
            wireframe: true,
            transparent: true,
            opacity: 0.15
        });
        const icosahedron = new THREE.Mesh(geometry2, material2);
        scene.add(icosahedron);

        camera.position.z = 5;

        // Mouse interaction
        let mouseX = 0;
        let mouseY = 0;
        document.addEventListener('mousemove', (event) => {
            mouseX = (event.clientX / window.innerWidth) - 0.5;
            mouseY = (event.clientY / window.innerHeight) - 0.5;
        });

        // Animation loop
        function animate() {
            requestAnimationFrame(animate);

            particles.rotation.y += 0.0002;
            particles.rotation.x += 0.0001;

            icosahedron.rotation.y += 0.005;
            icosahedron.rotation.x -= 0.002;

            // Camera movement
            camera.position.x += (mouseX * 2 - camera.position.x) * 0.05;
            camera.position.y += (-mouseY * 2 - camera.position.y) * 0.05;
            camera.lookAt(scene.position);

            renderer.render(scene, camera);
        }

        animate();

        // Handle resize
        window.addEventListener('resize', () => {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        });
    </script>
</body>
</html>
