<svg width="800" height="300" viewBox="0 0 800 300" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <filter id="liquid">
      <feTurbulence type="fractalNoise" baseFrequency="0.01" numOctaves="3">
        <animate attributeName="baseFrequency" values="0.01;0.015;0.01" dur="5s" repeatCount="indefinite" />
      </feTurbulence>
      <feDisplacementMap in="SourceGraphic" scale="10" />
    </filter>
  </defs>
  <rect width="800" height="300" fill="#050505"/>
  <text x="50%" y="50%" dominant-baseline="middle" text-anchor="middle" fill="white" font-family="serif" font-size="80" filter="url(#liquid)">
    SINGULARITY
  </text>
</svg>
