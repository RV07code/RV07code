<div align="center">
<!-- ═══════════════════════════════════════════════════════════════════ -->
<!--  T Y P O G R A P H I C   B R U T A L I S M                        -->
<!--  Pure HTML/CSS. Maximum density. No markdown weakness.             -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700;800&family=Inter:wght@300;400;600;900&display=swap');

  .brutal-container {
    font-family: 'Inter', -apple-system, sans-serif;
    max-width: 900px;
    margin: 0 auto;
    color: #000;
    line-height: 1.4;
  }

  .brutal-header {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 40px;
    align-items: end;
    border-bottom: 3px solid #000;
    padding-bottom: 30px;
    margin-bottom: 40px;
  }

  .brutal-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 48px;
    font-weight: 800;
    letter-spacing: -2px;
    line-height: 1;
    margin: 0;
  }

  .brutal-name span {
    display: block;
    font-size: 14px;
    font-weight: 400;
    letter-spacing: 4px;
    margin-top: 10px;
    color: #666;
  }

  .brutal-status {
    text-align: right;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
  }

  .brutal-status .indicator {
    display: inline-block;
    width: 8px;
    height: 8px;
    background: #000;
    border-radius: 50%;
    margin-right: 6px;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }

  .brutal-grid {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    gap: 20px;
    margin-bottom: 40px;
  }

  .brutal-card {
    border: 2px solid #000;
    padding: 20px;
    position: relative;
    overflow: hidden;
  }

  .brutal-card::before {
    content: attr(data-index);
    position: absolute;
    top: -10px;
    right: 15px;
    background: #fff;
    padding: 0 5px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 700;
  }

  .brutal-card.inverted {
    background: #000;
    color: #fff;
  }

  .brutal-card.inverted::before {
    background: #000;
    color: #fff;
  }

  .brutal-card.col-6 { grid-column: span 6; }
  .brutal-card.col-4 { grid-column: span 4; }
  .brutal-card.col-8 { grid-column: span 8; }
  .brutal-card.col-12 { grid-column: span 12; }

  .brutal-card h3 {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 2px;
    margin: 0 0 15px 0;
    text-transform: uppercase;
  }

  .brutal-metric {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    border-bottom: 1px solid #ddd;
    padding: 8px 0;
    font-size: 13px;
  }

  .brutal-metric:last-child { border-bottom: none; }

  .brutal-metric .label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #666;
    text-transform: uppercase;
    letter-spacing: 1px;
  }

  .brutal-metric .value {
    font-family: 'JetBrains Mono', monospace;
    font-weight: 700;
    font-size: 16px;
  }

  .brutal-bar {
    height: 3px;
    background: #eee;
    margin-top: 5px;
    position: relative;
  }

  .brutal-bar::after {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    height: 100%;
    background: #000;
    width: var(--fill);
  }

  .brutal-card.inverted .brutal-bar {
    background: #333;
  }

  .brutal-card.inverted .brutal-bar::after {
    background: #fff;
  }

  .skill-matrix {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
  }

  .skill-item {
    border: 1px solid #000;
    padding: 8px 12px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    transition: all 0.2s;
  }

  .skill-item:hover {
    background: #000;
    color: #fff;
    transform: translate(-2px, -2px);
    box-shadow: 4px 4px 0 #000;
  }

  .skill-level {
    font-size: 9px;
    color: #999;
  }

  .project-card {
    position: relative;
    padding-left: 20px;
    border-left: 3px solid #000;
  }

  .project-card h4 {
    font-family: 'JetBrains Mono', monospace;
    font-size: 18px;
    font-weight: 800;
    margin: 0 0 10px 0;
    letter-spacing: -1px;
  }

  .project-meta {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #666;
    margin-bottom: 10px;
  }

  .project-desc {
    font-size: 13px;
    line-height: 1.6;
    color: #333;
    margin-bottom: 15px;
  }

  .project-stats {
    display: flex;
    gap: 15px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
  }

  .project-stats span {
    display: flex;
    align-items: center;
    gap: 4px;
  }

  .heatmap {
    display: grid;
    grid-template-columns: repeat(52, 1fr);
    gap: 2px;
    height: 60px;
  }

  .heat-cell {
    background: #eee;
    border-radius: 1px;
  }

  .heat-cell.active { background: #000; }
  .heat-cell.medium { background: #666; }
  .heat-cell.light { background: #bbb; }

  .brutal-footer {
    border-top: 3px solid #000;
    margin-top: 40px;
    padding-top: 20px;
    display: grid;
    grid-template-columns: 1fr auto;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #666;
  }

  .contact-strip {
    display: flex;
    gap: 20px;
    margin-top: 20px;
  }

  .contact-strip a {
    color: #000;
    text-decoration: none;
    border-bottom: 2px solid #000;
    padding-bottom: 2px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    font-weight: 700;
    transition: all 0.2s;
  }

  .contact-strip a:hover {
    background: #000;
    color: #fff;
    padding: 2px 6px;
    border-bottom: 2px solid #000;
  }

  .tag-cloud {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tag {
    border: 1px solid #000;
    padding: 4px 10px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    font-weight: 700;
  }

  .tag.primary {
    background: #000;
    color: #fff;
  }

  .timeline {
    position: relative;
    padding-left: 20px;
  }

  .timeline::before {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    bottom: 0;
    width: 2px;
    background: #000;
  }

  .timeline-item {
    position: relative;
    padding-bottom: 20px;
  }

  .timeline-item::before {
    content: '';
    position: absolute;
    left: -24px;
    top: 2px;
    width: 8px;
    height: 8px;
    background: #fff;
    border: 2px solid #000;
    border-radius: 50%;
  }

  .timeline-item.active::before {
    background: #000;
  }

  .timeline-date {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #666;
    margin-bottom: 4px;
  }

  .timeline-content {
    font-size: 13px;
    font-weight: 600;
  }

  .ascii-art {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    line-height: 1.2;
    color: #000;
    white-space: pre;
    overflow-x: auto;
  }

  .brutal-divider {
    height: 2px;
    background: repeating-linear-gradient(
      90deg,
      #000 0px,
      #000 10px,
      transparent 10px,
      transparent 15px
    );
    margin: 30px 0;
  }
<div class="brutal-container">
  <!-- HEADER -->
<div class="brutal-header">
    <div>
      <div class="brutal-name">
        YOUR NAME
        <span>SYSTEMS ARCHITECT & PERFORMANCE ENGINEER</span>
      </div>
    </div>
    <div class="brutal-status">
      <span class="indicator"></span>ONLINE<br>
      UTC+8 · AVAILABLE FOR CONTRACT
    </div>
  </div>
  <!-- MAIN GRID -->
<div class="brutal-grid">
    <!-- LEFT: Core Metrics -->
    <div class="brutal-card col-4" data-index="01">
      <h3>Core Metrics</h3>
      <div class="brutal-metric">
        <span class="label">Commits</span>
        <span class="value">2,847</span>
      </div>
      <div class="brutal-bar" style="--fill: 78%"></div>

      <div class="brutal-metric">
        <span class="label">Pull Requests</span>
        <span class="value">1,203</span>
      </div>
      <div class="brutal-bar" style="--fill: 65%"></div>

      <div class="brutal-metric">
        <span class="label">Code Reviews</span>
        <span class="value">3,561</span>
      </div>
      <div class="brutal-bar" style="--fill: 92%"></div>

      <div class="brutal-metric">
        <span class="label">Issues Closed</span>
        <span class="value">892</span>
      </div>
      <div class="brutal-bar" style="--fill: 45%"></div>

      <div class="brutal-metric">
        <span class="label">Stars Earned</span>
        <span class="value">4.2k</span>
      </div>
      <div class="brutal-bar" style="--fill: 60%"></div>
    </div>

    <!-- CENTER: Activity Heatmap -->
    <div class="brutal-card inverted col-8" data-index="02">
      <h3>Contribution Topology</h3>
      <div class="heatmap">
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell light"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell light"></div>
<div class="heat-cell "></div>
<div class="heat-cell light"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell light"></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell light"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell light"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell light"></div>
<div class="heat-cell "></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell light"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell light"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell light"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell light"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell light"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell light"></div>
<div class="heat-cell light"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell light"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell light"></div>
<div class="heat-cell light"></div>
<div class="heat-cell "></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell light"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell medium"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell "></div>
<div class="heat-cell active"></div>
<div class="heat-cell active"></div>
<div class="heat-cell medium"></div>
<div class="heat-cell light"></div>
<div class="heat-cell active"></div>
<div class="heat-cell light"></div>
<div class="heat-cell medium"></div>
      </div>
      <div style="margin-top: 10px; font-family: 'JetBrains Mono', monospace; font-size: 9px; display: flex; justify-content: space-between; color: #666;">
        <span>JAN</span><span>FEB</span><span>MAR</span><span>APR</span><span>MAY</span><span>JUN</span>
        <span>JUL</span><span>AUG</span><span>SEP</span><span>OCT</span><span>NOV</span><span>DEC</span>
      </div>
    </div>
    <!-- ROW 2: Skills -->
    <div class="brutal-card inverted col-6" data-index="03">
      <h3>Language Arsenal</h3>
      <div class="skill-matrix">
        <div class="skill-item">Rust<span class="skill-level">PROD</span></div>
        <div class="skill-item">Go<span class="skill-level">PROD</span></div>
        <div class="skill-item">TypeScript<span class="skill-level">PROD</span></div>
        <div class="skill-item">C/C++<span class="skill-level">SYS</span></div>
        <div class="skill-item">Zig<span class="skill-level">EXP</span></div>
        <div class="skill-item">OCaml<span class="skill-level">EXP</span></div>
        <div class="skill-item">Python<span class="skill-level">AUTO</span></div>
        <div class="skill-item">SQL<span class="skill-level">PROD</span></div>
        <div class="skill-item">WASM<span class="skill-level">EXP</span></div>
      </div>
    </div>

    <div class="brutal-card col-6" data-index="04">
      <h3>Infrastructure & Tools</h3>
      <div class="skill-matrix">
        <div class="skill-item">Kubernetes<span class="skill-level">PROD</span></div>
        <div class="skill-item">Docker<span class="skill-level">PROD</span></div>
        <div class="skill-item">PostgreSQL<span class="skill-level">PROD</span></div>
        <div class="skill-item">Redis<span class="skill-level">PROD</span></div>
        <div class="skill-item">Kafka<span class="skill-level">PROD</span></div>
        <div class="skill-item">eBPF<span class="skill-level">EXP</span></div>
        <div class="skill-item">Nix<span class="skill-level">EXP</span></div>
        <div class="skill-item">Terraform<span class="skill-level">AUTO</span></div>
        <div class="skill-item">Git<span class="skill-level">PROD</span></div>
      </div>
    </div>

    <!-- ROW 3: Projects -->
    <div class="brutal-card col-6" data-index="05">
      <div class="project-card">
        <h4>NEXUS</h4>
        <div class="project-meta">v2.1.0 · MIT LICENSE · UPDATED 2 DAYS AGO</div>
        <div class="project-desc">
          Distributed consensus engine with zero-config clustering. 
          Sub-10ms leader election. Automatic rebalancing across failure domains.
        </div>
        <div class="project-stats">
          <span>★ 1,247</span>
          <span>⑃ 89</span>
          <span>◎ 12</span>
          <span>Rust 98%</span>
        </div>
      </div>
    </div>

    <div class="brutal-card inverted col-6" data-index="06">
      <div class="project-card" style="border-left-color: #fff;">
        <h4>VOID</h4>
        <div class="project-meta" style="color: #999;">v0.9.4 · GPL-3.0 · UPDATED 6 HOURS AGO</div>
        <div class="project-desc" style="color: #ccc;">
          Zero-allocation data pipeline for real-time analytics. 
          Lock-free queues. NUMA-aware scheduling. Sub-microsecond latency.
        </div>
        <div class="project-stats" style="color: #ccc;">
          <span>★ 892</span>
          <span>⑃ 45</span>
          <span>◎ 8</span>
          <span>C 88%</span>
        </div>
      </div>
    </div>

    <div class="brutal-card inverted col-6" data-index="07">
      <div class="project-card" style="border-left-color: #fff;">
        <h4>SPECTRE</h4>
        <div class="project-meta" style="color: #999;">v1.4.2 · APACHE-2.0 · UPDATED 1 WEEK AGO</div>
        <div class="project-desc" style="color: #ccc;">
          Declarative infrastructure orchestration. Pure function deployments. 
          Immutable infrastructure with state drift detection.
        </div>
        <div class="project-stats" style="color: #ccc;">
          <span>★ 634</span>
          <span>⑃ 34</span>
          <span>◎ 5</span>
          <span>Go 82%</span>
        </div>
      </div>
    </div>

    <div class="brutal-card col-6" data-index="08">
      <div class="project-card">
        <h4>AXIOM</h4>
        <div class="project-meta">v0.3.1 · MIT · UPDATED 3 DAYS AGO</div>
        <div class="project-desc">
          Experimental compiler for linearly-typed language. 
          Memory safety without GC. Compile-time resource management.
        </div>
        <div class="project-stats">
          <span>★ 456</span>
          <span>⑃ 23</span>
          <span>◎ 18</span>
          <span>OCaml 72%</span>
        </div>
      </div>
    </div>

    <!-- ROW 4: Timeline + ASCII -->
    <div class="brutal-card col-4" data-index="09">
      <h3>Chronology</h3>
      <div class="timeline">
        <div class="timeline-item active">
          <div class="timeline-date">2024 — PRESENT</div>
          <div class="timeline-content">Staff Engineer @ [Company]</div>
        </div>
        <div class="timeline-item">
          <div class="timeline-date">2021 — 2024</div>
          <div class="timeline-content">Senior Engineer @ [Company]</div>
        </div>
        <div class="timeline-item">
          <div class="timeline-date">2019 — 2021</div>
          <div class="timeline-content">Founding Engineer @ [Startup]</div>
        </div>
        <div class="timeline-item">
          <div class="timeline-date">2017 — 2019</div>
          <div class="timeline-content">Software Engineer @ [Corp]</div>
        </div>
        <div class="timeline-item">
          <div class="timeline-date">2013 — 2017</div>
          <div class="timeline-content">CS Degree @ [University]</div>
        </div>
      </div>
    </div>

    <div class="brutal-card inverted col-4" data-index="10">
      <h3>System Architecture</h3>
      <div class="ascii-art">
    ┌─────────────┐
    │   CLIENT    │
    └──────┬──────┘
           │ gRPC/mTLS
           ▼
    ┌─────────────┐     ┌─────────────┐
    │   API GW    │────▶│   RATE LIM  │
    └──────┬──────┘     └─────────────┘
           │
           ▼
    ┌─────────────────────────────────┐
    │      SERVICE MESH (mTLS)        │
    │  ┌─────┐ ┌─────┐ ┌─────┐       │
    │  │ SVC │ │ SVC │ │ SVC │       │
    │  │  A  │ │  B  │ │  C  │       │
    │  └──┬──┘ └──┬──┘ └──┬──┘       │
    │     └───────┼───────┘           │
    │             ▼                     │
    │      ┌───────────┐                │
    │      │  EVENT    │                │
    │      │   BUS     │                │
    │      └─────┬─────┘                │
    └────────────┼──────────────────────┘
                 │
        ┌────────┴────────┐
        ▼                 ▼
┌─────────┐       ┌─────────┐
│  WRITE  │       │  READ   │
│  NODE   │◄─────▶│  REPLICA│
│(PG/RAFT)│       │ (PG/RO) │
└─────────┘       └─────────┘
</div>
</div>
    <div class="brutal-card col-4" data-index="11">
      <h3>Operating Principles</h3>
      <div style="font-family: 'JetBrains Mono', monospace; font-size: 11px; line-height: 2;">
        <div>01. CLARITY > CLEVERNESS</div>
        <div>02. EXPLICIT > IMPLICIT</div>
        <div>03. COMPOSITION > INHERITANCE</div>
        <div>04. STABILITY > FEATURES</div>
        <div>05. SILENCE > NOISE</div>
        <div>06. DELETE > DOCUMENT</div>
        <div>07. MEASURE > ASSUME</div>
        <div>08. FAIL FAST > FAIL SILENT</div>
      </div>
    </div>

    <!-- ROW 5: Tags + Contact -->
    <div class="brutal-card inverted col-8" data-index="12">
      <h3>Interest Topology</h3>
      <div class="tag-cloud">
        <span class="tag primary">DISTRIBUTED SYSTEMS</span>
        <span class="tag">CONSENSUS ALGORITHMS</span>
        <span class="tag">MEMORY SAFETY</span>
        <span class="tag primary">ZERO-COPY</span>
        <span class="tag">KERNEL PROGRAMMING</span>
        <span class="tag">FORMAL METHODS</span>
        <span class="tag">LINEAR TYPES</span>
        <span class="tag primary">PERF ENGINEERING</span>
        <span class="tag">LOCK-FREE</span>
        <span class="tag">NUMA</span>
        <span class="tag">IO_URING</span>
        <span class="tag primary">EBPF</span>
        <span class="tag">WASM</span>
        <span class="tag">DECLARATIVE</span>
        <span class="tag">IMMUTABLE</span>
      </div>
    </div>

    <div class="brutal-card col-4" data-index="13">
      <h3>Contact Vector</h3>
      <div style="font-family: 'JetBrains Mono', monospace; font-size: 12px; line-height: 2.2;">
        <div>EMAIL: <a href="mailto:your@email.com" style="color: #000; text-decoration: none; border-bottom: 1px solid #000;">your@email.com</a></div>
        <div>WEB: <a href="https://your-website.com" style="color: #000; text-decoration: none; border-bottom: 1px solid #000;">your-website.com</a></div>
        <div>LINKEDIN: <a href="https://linkedin.com/in/yourprofile" style="color: #000; text-decoration: none; border-bottom: 1px solid #000;">/in/yourprofile</a></div>
        <div>GITHUB: <a href="https://github.com/YOUR_USERNAME" style="color: #000; text-decoration: none; border-bottom: 1px solid #000;">@YOUR_USERNAME</a></div>
      </div>
    </div>

</div>
  <!-- FOOTER -->
<div class="brutal-footer">
    <div>
      "The best code is no code. The second best deletes other code."<br>
      YOUR NAME · 2026 · ALL SYSTEMS NOMINAL
    </div>
    <div style="text-align: right;">
      <img src="https://komarev.com/ghpvc/?username=YOUR_USERNAME&color=000000&style=flat-square&label=VIEWS" />
    </div>
  </div>
</div>
</div>
