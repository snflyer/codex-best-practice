# codex-best-practice

<p align="center">
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 90" width="140" height="126">
  <style>
    .codex-body { animation: jump 0.5s ease-in-out infinite; transform-origin: center bottom; }
    .shadow     { animation: shadow-scale 0.5s ease-in-out infinite; }
    .left-arm   { animation: wave-left  0.5s ease-in-out infinite; transform-origin: right center; }
    .right-arm  { animation: wave-right 0.5s ease-in-out infinite; transform-origin: left center; }
    .left-ear   { animation: ear-bounce 0.5s ease-in-out infinite;       transform-origin: center bottom; }
    .right-ear  { animation: ear-bounce 0.5s ease-in-out infinite 0.1s;  transform-origin: center bottom; }
    .cursor     { animation: blink 1s step-end infinite; }

    @keyframes jump {
      0%, 100% { transform: translateY(0) scaleY(1) scaleX(1); }
      30% { transform: translateY(-16px) scaleY(1.1) scaleX(0.95); }
      50% { transform: translateY(-18px) scaleY(1.05) scaleX(0.98); }
      80% { transform: translateY(-5px) scaleY(0.95) scaleX(1.05); }
    }
    @keyframes shadow-scale { 0%,100% { transform: scaleX(1); opacity:.25; } 50% { transform: scaleX(.4); opacity:.08; } }
    @keyframes wave-left  { 0%,100% { transform: rotate(0); } 50% { transform: rotate(-25deg); } }
    @keyframes wave-right { 0%,100% { transform: rotate(0); } 50% { transform: rotate(25deg); } }
    @keyframes ear-bounce { 0%,100% { transform: scaleY(1); } 40% { transform: scaleY(1.2); } 60% { transform: scaleY(.85); } }
    @keyframes blink { 0%,50% { opacity:1; } 51%,100% { opacity:0; } }
  </style>

  <!-- 绳身=一条完整曲线;两端各加固定握把圆点;绳上字符=PHP的hello world程序 -->

  <!-- ========== 后绳(图层在下=身后),上升半圈可见 ========== -->
  <g>
    <path id="ropeBack" fill="none" stroke="#10A37F" stroke-width="0.4" stroke-dasharray="1 2">
      <animate attributeName="d" dur="0.5s" repeatCount="indefinite" keyTimes="0;0.25;0.5;0.75;1"
        values="M8 40 Q50 -30 92 40; M8 40 Q50 40 92 40; M8 40 Q50 125 92 40; M8 40 Q50 40 92 40; M8 40 Q50 -30 92 40"/>
      <animate attributeName="opacity" dur="0.5s" repeatCount="indefinite" calcMode="discrete" keyTimes="0;0.5;1" values="0;1;0"/>
    </path>
    <text font-family="ui-monospace, monospace" font-size="5" font-weight="bold" fill="#10A37F">
      <animate attributeName="opacity" dur="0.5s" repeatCount="indefinite" calcMode="discrete" keyTimes="0;0.5;1" values="0;1;0"/>
      <textPath href="#ropeBack" startOffset="0">&lt;?php echo &quot;hello world&quot;;
        <animate attributeName="startOffset" dur="0.5s" repeatCount="indefinite" values="0;10%"/>
      </textPath>
    </text>
  </g>

  <!-- Shadow -->
  <ellipse class="shadow" cx="50" cy="82" rx="22" ry="5" fill="#000"/>

  <!-- ========== Codex 角色 ========== -->
  <g class="codex-body">
    <rect class="left-ear"  x="22" y="10" width="6" height="14" fill="#1A1A1A"/>
    <circle class="left-ear" cx="25" cy="9" r="3" fill="#10A37F"/>
    <rect class="right-ear" x="72" y="10" width="6" height="14" fill="#1A1A1A"/>
    <circle class="right-ear" cx="75" cy="9" r="3" fill="#10A37F"/>
    <rect x="18" y="24" width="64" height="4" fill="#1A1A1A"/>
    <rect x="14" y="28" width="72" height="32" rx="3" fill="#1A1A1A"/>
    <rect x="22" y="33" width="56" height="20" rx="2" fill="#0D0D0D"/>
    <path d="M30 40 L35 43.5 L30 47" fill="none" stroke="#10A37F" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
    <rect x="38" y="46" width="8" height="2.5" fill="#10A37F"/>
    <rect class="cursor" x="50" y="38" width="4" height="10" fill="#10A37F"/>
    <rect class="left-arm"  x="2"  y="36" width="12" height="8" rx="2" fill="#1A1A1A"/>
    <rect class="right-arm" x="86" y="36" width="12" height="8" rx="2" fill="#1A1A1A"/>
    <rect x="24" y="60" width="12" height="14" rx="2" fill="#1A1A1A"/>
    <rect x="64" y="60" width="12" height="14" rx="2" fill="#1A1A1A"/>
  </g>

  <!-- ========== 前绳(图层在上=身前),下落半圈可见 ========== -->
  <g>
    <path id="ropeFront" fill="none" stroke="#10A37F" stroke-width="0.4" stroke-dasharray="1 2">
      <animate attributeName="d" dur="0.5s" repeatCount="indefinite" keyTimes="0;0.25;0.5;0.75;1"
        values="M8 40 Q50 -30 92 40; M8 40 Q50 40 92 40; M8 40 Q50 125 92 40; M8 40 Q50 40 92 40; M8 40 Q50 -30 92 40"/>
      <animate attributeName="opacity" dur="0.5s" repeatCount="indefinite" calcMode="discrete" keyTimes="0;0.5;1" values="1;0;1"/>
    </path>
    <text font-family="ui-monospace, monospace" font-size="5" font-weight="bold" fill="#10A37F">
      <animate attributeName="opacity" dur="0.5s" repeatCount="indefinite" calcMode="discrete" keyTimes="0;0.5;1" values="1;0;1"/>
      <textPath href="#ropeFront" startOffset="0">&lt;?php echo &quot;hello world&quot;;
        <animate attributeName="startOffset" dur="0.5s" repeatCount="indefinite" values="0;10%"/>
      </textPath>
    </text>
  </g>

  <!-- ========== 两端固定握把圆点 ========== -->
  <g fill="#10A37F">
    <circle cx="8"  cy="40" r="1.1"/>
    <circle cx="92" cy="40" r="1.1"/>
  </g>
</svg>
</p>

## Wait... where are the Codex tips?

Haha, you got tricked.

There are no Codex best practices here.

There is only a jumping Codex.

I saw the jumping Claude Code icon in `claude-code-best-practice` and thought it was too cute, so I made this repo for Codex.

That is the whole idea.

No deep guide. No secret tricks. Just a little joke and a tiny green robot doing jump rope.
