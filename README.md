<div align="center">

<svg width="800" height="500" viewBox="0 0 800 500" xmlns="http://www.w3.org/2000/svg" style="max-width:100%;">

  <!-- DEFS -->
  <defs>
    <!-- Grid pattern -->
    <pattern id="grid" width="40" height="40" patternUnits="userSpaceOnUse">
      <path d="M 40 0 L 0 0 0 40" fill="none" stroke="#eee" stroke-width="0.5"/>
    </pattern>

    <!-- Noise filter for texture -->
    <filter id="noise">
      <feTurbulence type="fractalNoise" baseFrequency="0.9" numOctaves="3" stitchTiles="stitch"/>
      <feColorMatrix type="saturate" values="0"/>
      <feComponentTransfer>
        <feFuncA type="linear" slope="0.05"/>
      </feComponentTransfer>
    </filter>

    <!-- Glow for active elements -->
    <filter id="glow" x="-20%" y="-20%" width="140%" height="140%">
      <feGaussianBlur stdDeviation="2" result="blur"/>
      <feMerge>
        <feMergeNode in="blur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>

  <!-- BACKGROUND -->
  <rect width="800" height="500" fill="#fafafa"/>
  <rect width="800" height="500" fill="url(#grid)"/>
  <rect width="800" height="500" filter="url(#noise)"/>

  <!-- ═══════════════════════════════════════════════════════════════ -->
  <!--  WINDOW CHROME                                                  -->
  <!-- ═══════════════════════════════════════════════════════════════ -->

  <!-- Window border -->
  <rect x="20" y="20" width="760" height="460" fill="none" stroke="#000" stroke-width="2"/>

  <!-- Title bar -->
  <rect x="20" y="20" width="760" height="32" fill="#000"/>
  <text x="40" y="42" fill="#fff" font-family="JetBrains Mono, monospace" font-size="11" font-weight="700" letter-spacing="2">SYSTEM.MONITOR // YOUR_NAME</text>

  <!-- Window controls -->
  <circle cx="740" cy="36" r="6" fill="#fff" opacity="0.3"/>
  <circle cx="720" cy="36" r="6" fill="#fff" opacity="0.3"/>
  <circle cx="700" cy="36" r="6" fill="#fff" opacity="0.3"/>

  <!-- Status bar bottom -->
  <rect x="20" y="468" width="760" height="12" fill="#000"/>
  <text x="40" y="477" fill="#fff" font-family="JetBrains Mono, monospace" font-size="8" opacity="0.6">READY  //  MEM: OPTIMAL  //  CPU: IDLE</text>
  <text x="720" y="477" fill="#fff" font-family="JetBrains Mono, monospace" font-size="8" opacity="0.6" text-anchor="end">v2.0.1</text>

  <!-- ═══════════════════════════════════════════════════════════════ -->
  <!--  LEFT SIDEBAR — Navigation Tree                                 -->
  <!-- ═══════════════════════════════════════════════════════════════ -->

  <rect x="20" y="52" width="160" height="416" fill="none" stroke="#000" stroke-width="1"/>
  <line x1="20" y1="72" x2="180" y2="72" stroke="#000" stroke-width="1"/>
  <text x="35" y="66" fill="#000" font-family="JetBrains Mono, monospace" font-size="9" font-weight="700" letter-spacing="1">NAVIGATION</text>

  <!-- Tree items -->
  <g font-family="JetBrains Mono, monospace" font-size="10" fill="#000">
    <text x="35" y="95">▸ identity</text>
    <text x="35" y="115">▸ projects</text>
    <text x="35" y="135">▸ telemetry</text>
    <text x="35" y="155">▸ contact</text>

    <text x="35" y="185" opacity="0.3">─</text>
    <text x="35" y="205" opacity="0.3">─</text>
    <text x="35" y="225" opacity="0.3">─</text>

    <!-- Active indicator -->
    <rect x="28" y="138" width="4" height="10" fill="#000"/>
  </g>

  <!-- ═══════════════════════════════════════════════════════════════ -->
  <!--  CENTER PANEL — Main Content Area                               -->
  <!-- ═══════════════════════════════════════════════════════════════ -->

  <rect x="180" y="52" width="600" height="416" fill="none" stroke="#000" stroke-width="1"/>

  <!-- Sub-panel: Identity -->
  <rect x="200" y="72" width="260" height="140" fill="none" stroke="#000" stroke-width="1"/>
  <rect x="200" y="72" width="260" height="20" fill="#000"/>
  <text x="210" y="86" fill="#fff" font-family="JetBrains Mono, monospace" font-size="9" font-weight="700">IDENTITY.LOG</text>

  <g font-family="JetBrains Mono, monospace" font-size="10" fill="#000">
    <text x="210" y="110"><tspan fill="#666">entity</tspan>     human</text>
    <text x="210" y="128"><tspan fill="#666">function</tspan>   architect</text>
    <text x="210" y="146"><tspan fill="#666">runtime</tspan>    ~15y</text>
    <text x="210" y="164"><tspan fill="#666">state</tspan>      active</text>
    <text x="210" y="182"><tspan fill="#666">stack</tspan>      rust go c</text>
  </g>

  <!-- Sub-panel: Live Clock -->
  <rect x="480" y="72" width="280" height="140" fill="#000"/>
  <text x="620" y="110" fill="#fff" font-family="JetBrains Mono, monospace" font-size="36" font-weight="300" text-anchor="middle" letter-spacing="4">
    <tspan id="clock">00:00:00</tspan>
  </text>
  <text x="620" y="130" fill="#666" font-family="JetBrains Mono, monospace" font-size="9" text-anchor="middle" letter-spacing="2">UTC+8 // LIVE</text>

  <!-- Clock hands animation -->
  <line x1="620" y1="145" x2="620" y2="165" stroke="#fff" stroke-width="1" opacity="0.5">
    <animateTransform attributeName="transform" type="rotate" from="0 620 145" to="360 620 145" dur="60s" repeatCount="indefinite"/>
  </line>

  <!-- Sub-panel: Projects -->
  <rect x="200" y="232" width="560" height="140" fill="none" stroke="#000" stroke-width="1"/>
  <rect x="200" y="232" width="560" height="20" fill="#000"/>
  <text x="210" y="246" fill="#fff" font-family="JetBrains Mono, monospace" font-size="9" font-weight="700">PROJECTS.DIR</text>

  <!-- Project cards within panel -->
  <g font-family="JetBrains Mono, monospace" font-size="10" fill="#000">
    <!-- Card 1 -->
    <rect x="210" y="262" width="120" height="90" fill="none" stroke="#000" stroke-width="1"/>
    <rect x="210" y="262" width="120" height="16" fill="#000"/>
    <text x="216" y="274" fill="#fff" font-size="8">NEXUS</text>
    <text x="216" y="295" font-size="9">consensus</text>
    <text x="216" y="310" font-size="9">engine</text>
    <text x="216" y="335" font-size="8" opacity="0.5">rust 98%</text>

    <!-- Card 2 -->
    <rect x="340" y="262" width="120" height="90" fill="#000"/>
    <text x="346" y="274" fill="#fff" font-size="8">VOID</text>
    <text x="346" y="295" fill="#fff" font-size="9">zero-copy</text>
    <text x="346" y="310" fill="#fff" font-size="9">pipeline</text>
    <text x="346" y="335" fill="#666" font-size="8">c 88%</text>

    <!-- Card 3 -->
    <rect x="470" y="262" width="120" height="90" fill="none" stroke="#000" stroke-width="1"/>
    <rect x="470" y="262" width="120" height="16" fill="#000"/>
    <text x="476" y="274" fill="#fff" font-size="8">SPECTRE</text>
    <text x="476" y="295" font-size="9">declarative</text>
    <text x="476" y="310" font-size="9">infra</text>
    <text x="476" y="335" font-size="8" opacity="0.5">go 82%</text>

    <!-- Card 4 -->
    <rect x="600" y="262" width="150" height="90" fill="#000"/>
    <text x="606" y="274" fill="#fff" font-size="8">AXIOM</text>
    <text x="606" y="295" fill="#fff" font-size="9">linear types</text>
    <text x="606" y="310" fill="#fff" font-size="9">compiler</text>
    <text x="606" y="335" fill="#666" font-size="8">ocaml 72%</text>
  </g>

  <!-- Sub-panel: Telemetry / Waveform -->
  <rect x="200" y="392" width="560" height="56" fill="none" stroke="#000" stroke-width="1"/>
  <rect x="200" y="392" width="560" height="16" fill="#000"/>
  <text x="210" y="404" fill="#fff" font-family="JetBrains Mono, monospace" font-size="8" font-weight="700">TELEMETRY.WAVEFORM</text>

  <!-- Animated waveform lines -->
  <g stroke="#000" stroke-width="1" fill="none">
    <path d="M210,420 Q230,410 250,420 T290,420 T330,420 T370,420 T410,420 T450,420 T490,420 T530,420 T570,420 T610,420 T650,420 T690,420 T730,420">
      <animate attributeName="d" 
        values="M210,420 Q230,410 250,420 T290,420 T330,420 T370,420 T410,420 T450,420 T490,420 T530,420 T570,420 T610,420 T650,420 T690,420 T730,420;
                M210,420 Q230,430 250,420 T290,420 T330,420 T370,420 T410,420 T450,420 T490,420 T530,420 T570,420 T610,420 T650,420 T690,420 T730,420;
                M210,420 Q230,410 250,420 T290,420 T330,420 T370,420 T410,420 T450,420 T490,420 T530,420 T570,420 T610,420 T650,420 T690,420 T730,420" 
        dur="4s" repeatCount="indefinite"/>
    </path>
    <path d="M210,435 Q230,425 250,435 T290,435 T330,435 T370,435 T410,435 T450,435 T490,435 T530,435 T570,435 T610,435 T650,435 T690,435 T730,435" opacity="0.3">
      <animate attributeName="d" 
        values="M210,435 Q230,425 250,435 T290,435 T330,435 T370,435 T410,435 T450,435 T490,435 T530,435 T570,435 T610,435 T650,435 T690,435 T730,435;
                M210,435 Q230,445 250,435 T290,435 T330,435 T370,435 T410,435 T450,435 T490,435 T530,435 T570,435 T610,435 T650,435 T690,435 T730,435;
                M210,435 Q230,425 250,435 T290,435 T330,435 T370,435 T410,435 T450,435 T490,435 T530,435 T570,435 T610,435 T650,435 T690,435 T730,435" 
        dur="6s" repeatCount="indefinite"/>
    </path>
  </g>

  <!-- ═══════════════════════════════════════════════════════════════ -->
  <!--  DECORATIVE ELEMENTS                                            -->
  <!-- ═══════════════════════════════════════════════════════════════ -->

  <!-- Corner brackets -->
  <path d="M20,20 L40,20 M20,20 L20,40" stroke="#000" stroke-width="3" fill="none"/>
  <path d="M780,20 L760,20 M780,20 L780,40" stroke="#000" stroke-width="3" fill="none"/>
  <path d="M20,480 L40,480 M20,480 L20,460" stroke="#000" stroke-width="3" fill="none"/>
  <path d="M780,480 L760,480 M780,480 L780,460" stroke="#000" stroke-width="3" fill="none"/>

  <!-- Scanline effect -->
  <rect x="20" y="52" width="760" height="1" fill="#000" opacity="0.05">
    <animate attributeName="y" values="52;468;52" dur="8s" repeatCount="indefinite"/>
  </rect>

  <!-- Pulsing dot -->
  <circle cx="35" cy="36" r="3" fill="#fff">
    <animate attributeName="opacity" values="1;0.3;1" dur="2s" repeatCount="indefinite"/>
  </circle>

</svg>

<br>

<!-- Contact links below the window -->
<a href="mailto:your@email.com" style="color:#000; text-decoration:none; border-bottom:1px solid #000; font-family:monospace; font-size:10px;">email</a>
<span style="color:#999; font-family:monospace; font-size:10px;"> · </span>
<a href="https://your-website.com" style="color:#000; text-decoration:none; border-bottom:1px solid #000; font-family:monospace; font-size:10px;">web</a>
<span style="color:#999; font-family:monospace; font-size:10px;"> · </span>
<a href="https://github.com/YOUR_USERNAME" style="color:#000; text-decoration:none; border-bottom:1px solid #000; font-family:monospace; font-size:10px;">github</a>

</div>
