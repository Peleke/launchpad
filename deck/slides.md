---
theme: default
title: 'Production Agent Engineering — Validation Summary'
info: |
  Hunter pipeline validation results for Production Agent Engineering cohort + security workshop.
  Built 2026-03-05.
class: text-white
drawings:
  persist: false
transition: slide-left
css: unocss
---

<style>
@import url('https://fonts.googleapis.com/css2?family=Caveat:wght@400;700&display=swap');
:root {
  --slidev-theme-primary: #e88072;
  --slidev-theme-default: #e6edf3;
}
.slidev-layout {
  background: #0d1117 !important;
  color: #e6edf3;
}
h1, h2, h3 { color: #eee0cc; }
.coral { color: #e88072; }
.green { color: #4ade80; }
.red { color: #f87171; }
.muted { color: #8b949e; }
.stat-big { font-size: 3rem; font-weight: 800; color: #e88072; }
blockquote { border-left: 3px solid #e88072; padding: 8px 16px; background: rgba(232,128,114,0.06); border-radius: 0 6px 6px 0; }
blockquote p { color: #e6edf3; font-style: italic; }
blockquote cite { color: #8b949e; font-size: 0.8rem; }
</style>

---
layout: cover
background: '#0d1117'
---

# Production Agent Engineering

<p class="text-2xl coral">Validation Summary — 2026-03-05</p>

<p class="muted text-sm mt-8">Hunter Pipeline: signal-scan → decision-log → persona-extract → offer-scope → pitch → assets</p>

---

## The Opportunity

<div style="display:flex;justify-content:center;margin:16px 0;">
<svg viewBox="0 0 700 320" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:700px;">
  <defs>
    <filter id="roughen-1" x="-2%" y="-2%" width="104%" height="104%">
      <feTurbulence type="turbulence" baseFrequency="0.03" numOctaves="2" result="noise" seed="1"/>
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="1.2" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
    <filter id="glow-1">
      <feGaussianBlur stdDeviation="3" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>
  <!-- Left cluster: Courses -->
  <g filter="url(#roughen-1)" transform="rotate(-0.5, 130, 140)">
    <path d="M 30,60 C 32,58 148,57 150,60 C 152,62 153,108 150,110 C 148,112 32,113 30,110 C 28,108 28,62 30,60 Z" fill="none" stroke="#888888" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="90" y="90" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#888888">Andrew Ng</text>
  </g>
  <g filter="url(#roughen-1)" transform="rotate(0.8, 130, 140)">
    <path d="M 30,120 C 33,118 147,117 150,120 C 152,122 153,168 150,170 C 147,172 33,173 30,170 C 28,168 28,122 30,120 Z" fill="none" stroke="#888888" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="90" y="150" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#888888">Udemy / Coursera</text>
  </g>
  <g filter="url(#roughen-1)" transform="rotate(-0.3, 130, 200)">
    <path d="M 30,180 C 32,178 148,177 150,180 C 152,182 153,228 150,230 C 148,232 32,233 30,230 C 28,228 28,182 30,180 Z" fill="none" stroke="#888888" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="90" y="210" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#888888">Anthropic Academy</text>
  </g>
  <g filter="url(#roughen-1)" transform="rotate(0.5, 130, 260)">
    <path d="M 30,240 C 33,238 147,237 150,240 C 152,242 153,278 150,280 C 148,282 32,283 30,280 C 28,278 28,242 30,240 Z" fill="none" stroke="#888888" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="90" y="264" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#888888">Skool / Agency</text>
  </g>
  <text x="90" y="35" text-anchor="middle" font-family="'Caveat', cursive" font-size="20" fill="#888888" font-weight="700">COURSES</text>
  <!-- Right side: Production -->
  <g filter="url(#roughen-1)" transform="rotate(-0.4, 590, 160)">
    <path d="M 530,80 C 533,77 647,76 650,80 C 653,83 654,238 650,240 C 647,243 533,244 530,240 C 527,237 527,83 530,80 Z" fill="none" stroke="#e88072" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="590" y="150" text-anchor="middle" font-family="'Caveat', cursive" font-size="22" fill="#e88072" font-weight="700">PRODUCTION</text>
    <!-- Alarm indicators -->
    <circle cx="555" cy="200" r="8" fill="#f87171" opacity="0.8"/>
    <circle cx="590" cy="200" r="8" fill="#f87171" opacity="0.6"/>
    <circle cx="625" cy="200" r="8" fill="#f87171" opacity="0.9"/>
    <text x="590" y="230" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#f87171">alerts firing</text>
  </g>
  <text x="590" y="55" text-anchor="middle" font-family="'Caveat', cursive" font-size="20" fill="#e88072" font-weight="700">PRODUCTION</text>
  <!-- The Gap -->
  <line x1="170" y1="160" x2="510" y2="160" stroke="#eee0cc" stroke-width="2" stroke-dasharray="12,8" opacity="0.5"/>
  <line x1="170" y1="140" x2="170" y2="180" stroke="#eee0cc" stroke-width="2" opacity="0.4"/>
  <line x1="510" y1="140" x2="510" y2="180" stroke="#eee0cc" stroke-width="2" opacity="0.4"/>
  <g filter="url(#glow-1)">
    <rect x="250" y="120" width="200" height="50" rx="8" fill="rgba(248,113,113,0.12)" stroke="none"/>
    <text x="350" y="142" text-anchor="middle" font-family="'Caveat', cursive" font-size="22" fill="#f87171" font-weight="700">80–90% die here</text>
    <text x="350" y="162" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#8b949e">(RAND Corporation)</text>
  </g>
  <!-- Downward arrow into gap -->
  <path d="M 350,85 C 350,90 348,105 350,115" stroke="#f87171" stroke-width="2" fill="none" marker-end="url(#arrow-gap)"/>
  <defs>
    <marker id="arrow-gap" viewBox="0 0 12 10" refX="10" refY="5" markerWidth="8" markerHeight="6" orient="auto-start-reverse" fill="none" stroke="#f87171" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
      <path d="M 1,1 L 10,5 L 1,9"/>
    </marker>
  </defs>
  <text x="350" y="300" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc" opacity="0.7">THE GAP</text>
</svg>
</div>

<p class="text-center text-lg mt-2">Every course teaches how to <span class="coral">build</span> an agent. Nobody teaches why <span class="red">90% die in production</span>.</p>

---

## Evidence Wall

<div style="display:flex;justify-content:center;margin:16px 0;">
<svg viewBox="0 0 720 400" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:720px;">
  <defs>
    <filter id="roughen-2" x="-2%" y="-2%" width="104%" height="104%">
      <feTurbulence type="turbulence" baseFrequency="0.03" numOctaves="2" result="noise" seed="2"/>
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="1.2" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
  </defs>
  <!-- Sticky note 1 -->
  <g filter="url(#roughen-2)" transform="rotate(-2.5, 110, 110)">
    <path d="M 20,30 C 23,27 197,26 200,30 C 203,33 204,188 200,190 C 197,193 23,194 20,190 C 17,187 17,33 20,30 Z" fill="rgba(232,128,114,0.08)" stroke="#e88072" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="110" y="85" text-anchor="middle" font-family="'Caveat', cursive" font-size="42" fill="#e88072" font-weight="700">94%</text>
    <text x="110" y="120" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc">skills gap</text>
    <text x="110" y="165" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#8b949e">GlobeNewsWire</text>
    <text x="110" y="182" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#8b949e">2024 Survey</text>
  </g>
  <!-- Sticky note 2 -->
  <g filter="url(#roughen-2)" transform="rotate(1.5, 350, 100)">
    <path d="M 260,20 C 263,17 437,18 440,20 C 443,23 444,178 440,180 C 437,183 263,182 260,180 C 257,177 257,23 260,20 Z" fill="rgba(78,222,128,0.06)" stroke="#4ade80" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="350" y="75" text-anchor="middle" font-family="'Caveat', cursive" font-size="42" fill="#4ade80" font-weight="700">70%</text>
    <text x="350" y="110" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc">wrong answers</text>
    <text x="350" y="148" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#8b949e">Carnegie Mellon</text>
    <text x="350" y="168" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#8b949e">tool-use study</text>
  </g>
  <!-- Sticky note 3 -->
  <g filter="url(#roughen-2)" transform="rotate(-1.0, 590, 110)">
    <path d="M 500,30 C 503,27 677,28 680,30 C 683,33 684,188 680,190 C 677,193 503,192 500,190 C 497,187 497,33 500,30 Z" fill="rgba(248,113,113,0.08)" stroke="#f87171" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="590" y="85" text-anchor="middle" font-family="'Caveat', cursive" font-size="42" fill="#f87171" font-weight="700">95%</text>
    <text x="590" y="120" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc">zero value</text>
    <text x="590" y="160" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#8b949e">MIT Sloan</text>
    <text x="590" y="178" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#8b949e">enterprise AI ROI</text>
  </g>
  <!-- Sticky note 4 -->
  <g filter="url(#roughen-2)" transform="rotate(2.0, 180, 310)">
    <path d="M 70,220 C 73,217 287,218 290,220 C 293,223 294,378 290,380 C 287,383 73,382 70,380 C 67,377 67,223 70,220 Z" fill="rgba(232,128,114,0.06)" stroke="#eee0cc" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" opacity="0.7"/>
    <text x="180" y="278" text-anchor="middle" font-family="'Caveat', cursive" font-size="32" fill="#e88072" font-weight="700">40% → 29%</text>
    <text x="180" y="312" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc">trust collapse</text>
    <text x="180" y="350" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#8b949e">Stack Overflow</text>
    <text x="180" y="368" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#8b949e">Dev Survey 2024</text>
  </g>
  <!-- Sticky note 5 -->
  <g filter="url(#roughen-2)" transform="rotate(-1.8, 500, 310)">
    <path d="M 380,225 C 383,222 617,221 620,225 C 623,228 624,383 620,385 C 617,388 383,389 380,385 C 377,382 377,228 380,225 Z" fill="rgba(248,113,113,0.06)" stroke="#f87171" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" opacity="0.8"/>
    <text x="500" y="280" text-anchor="middle" font-family="'Caveat', cursive" font-size="28" fill="#f87171" font-weight="700">674 pts</text>
    <text x="500" y="318" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc">"reinvented programming,</text>
    <text x="500" y="340" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc">badly"</text>
    <text x="500" y="373" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#8b949e">r/ExperiencedDevs</text>
  </g>
</svg>
</div>

---

## Reddit Voices

> "The worst part is I can't figure out WHERE things go wrong. Is it the retrieval? The tool selection? The synthesis?"
>
> <cite>— r/AI_Agents (10 upvotes)</cite>

<br/>

> "Frameworks get you to a demo, but prod failure modes are mostly systems problems"
>
> <cite>— u/Santoshr93, r/ExperiencedDevs</cite>

<br/>

> "No, but many will pretend they did to sell their services"
>
> <cite>— r/AI_Agents (20 upvotes), on "Has anyone actually deployed agents to production?"</cite>

---

## SDP Scoring

<div style="display:flex;justify-content:center;margin:16px 0;">
<svg viewBox="0 0 700 350" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:700px;">
  <defs>
    <filter id="roughen-3" x="-2%" y="-2%" width="104%" height="104%">
      <feTurbulence type="turbulence" baseFrequency="0.03" numOctaves="2" result="noise" seed="3"/>
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="1.2" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
    <filter id="glow-3">
      <feGaussianBlur stdDeviation="4" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>
  <text x="350" y="30" text-anchor="middle" font-family="'Caveat', cursive" font-size="20" fill="#eee0cc" font-weight="700">Opportunity Ranking (Score / 60)</text>
  <!-- Bar 1: Production Cohort — highlighted -->
  <g filter="url(#roughen-3)">
    <text x="195" y="78" text-anchor="end" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc">Production Cohort</text>
    <g filter="url(#glow-3)">
      <path d="M 210,58 C 213,55 617,54 620,58 C 623,61 624,88 620,90 C 617,93 213,94 210,90 C 207,87 207,61 210,58 Z" fill="rgba(232,128,114,0.25)" stroke="#e88072" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
    </g>
    <text x="635" y="80" font-family="'Caveat', cursive" font-size="20" fill="#e88072" font-weight="700">50/60</text>
  </g>
  <!-- Bar 2: Security Workshop -->
  <g filter="url(#roughen-3)">
    <text x="195" y="138" text-anchor="end" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc">Security Workshop</text>
    <path d="M 210,118 C 213,115 557,114 560,118 C 563,121 564,148 560,150 C 557,153 213,154 210,150 C 207,147 207,121 210,118 Z" fill="rgba(232,128,114,0.15)" stroke="#e88072" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="575" y="140" font-family="'Caveat', cursive" font-size="18" fill="#e88072">45/60</text>
  </g>
  <!-- Bar 3: Context Engineering -->
  <g filter="url(#roughen-3)">
    <text x="195" y="198" text-anchor="end" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc">Context Engineering</text>
    <path d="M 210,178 C 213,175 467,174 470,178 C 473,181 474,208 470,210 C 467,213 213,214 210,210 C 207,207 207,181 210,178 Z" fill="rgba(232,128,114,0.10)" stroke="#e88072" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="485" y="200" font-family="'Caveat', cursive" font-size="18" fill="#e88072">38/60</text>
  </g>
  <!-- Bar 4: Observability Toolkit -->
  <g filter="url(#roughen-3)">
    <text x="195" y="258" text-anchor="end" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc">Observability Toolkit</text>
    <path d="M 210,238 C 213,235 447,234 450,238 C 453,241 454,268 450,270 C 447,273 213,274 210,270 C 207,267 207,241 210,238 Z" fill="rgba(232,128,114,0.08)" stroke="#e88072" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="465" y="260" font-family="'Caveat', cursive" font-size="18" fill="#e88072">36/60</text>
  </g>
  <!-- Bar 5: Do Nothing -->
  <g filter="url(#roughen-3)">
    <text x="195" y="318" text-anchor="end" font-family="'Caveat', cursive" font-size="18" fill="#888888">Do Nothing</text>
    <path d="M 210,298 C 213,295 347,294 350,298 C 353,301 354,328 350,330 C 347,333 213,334 210,330 C 207,327 207,301 210,298 Z" fill="rgba(136,136,136,0.08)" stroke="#888888" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="365" y="320" font-family="'Caveat', cursive" font-size="18" fill="#888888">20/60</text>
  </g>
</svg>
</div>

---

## Three Personas

<div style="display:flex;justify-content:center;margin:16px 0;">
<svg viewBox="0 0 750 340" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:750px;">
  <defs>
    <filter id="roughen-4" x="-2%" y="-2%" width="104%" height="104%">
      <feTurbulence type="turbulence" baseFrequency="0.03" numOctaves="2" result="noise" seed="4"/>
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="1.2" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
  </defs>
  <!-- Card 1: Midnight Firefighter -->
  <g filter="url(#roughen-4)" transform="rotate(-0.8, 130, 170)">
    <path d="M 15,25 C 18,22 232,21 235,25 C 238,28 239,308 235,310 C 232,313 18,314 15,310 C 12,307 12,28 15,25 Z" fill="rgba(232,128,114,0.06)" stroke="#e88072" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <circle cx="125" cy="75" r="30" fill="#e88072" opacity="0.9"/>
    <text x="125" y="82" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="white" font-weight="700">3-8 YOE</text>
    <text x="125" y="130" text-anchor="middle" font-family="'Caveat', cursive" font-size="19" fill="#eee0cc" font-weight="700">The Midnight</text>
    <text x="125" y="155" text-anchor="middle" font-family="'Caveat', cursive" font-size="19" fill="#eee0cc" font-weight="700">Firefighter</text>
    <line x1="50" y1="170" x2="200" y2="170" stroke="#e88072" stroke-width="1" opacity="0.3"/>
    <text x="125" y="200" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#8b949e">"2 AM debugging</text>
    <text x="125" y="220" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#8b949e">a black box"</text>
    <line x1="50" y1="245" x2="200" y2="245" stroke="#e88072" stroke-width="1" opacity="0.3"/>
    <text x="125" y="270" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#4ade80">WTP: $500–1K</text>
    <text x="125" y="295" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#8b949e">Maven cohort</text>
  </g>
  <!-- Card 2: Reluctant Architect -->
  <g filter="url(#roughen-4)" transform="rotate(0.5, 380, 170)">
    <path d="M 265,25 C 268,22 492,21 495,25 C 498,28 499,308 495,310 C 492,313 268,314 265,310 C 262,307 262,28 265,25 Z" fill="rgba(232,128,114,0.06)" stroke="#e88072" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <circle cx="380" cy="75" r="30" fill="#e88072" opacity="0.9"/>
    <text x="380" y="82" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="white" font-weight="700">5-15 YOE</text>
    <text x="380" y="130" text-anchor="middle" font-family="'Caveat', cursive" font-size="19" fill="#eee0cc" font-weight="700">The Reluctant</text>
    <text x="380" y="155" text-anchor="middle" font-family="'Caveat', cursive" font-size="19" fill="#eee0cc" font-weight="700">Architect</text>
    <line x1="300" y1="170" x2="460" y2="170" stroke="#e88072" stroke-width="1" opacity="0.3"/>
    <text x="380" y="200" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#8b949e">"Staff said go agentic,</text>
    <text x="380" y="220" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#8b949e">I said prove it"</text>
    <line x1="300" y1="245" x2="460" y2="245" stroke="#e88072" stroke-width="1" opacity="0.3"/>
    <text x="380" y="270" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#4ade80">WTP: $750–1.5K</text>
    <text x="380" y="295" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#8b949e">Maven cohort</text>
  </g>
  <!-- Card 3: Security-Conscious Lead -->
  <g filter="url(#roughen-4)" transform="rotate(-0.3, 625, 170)">
    <path d="M 510,25 C 513,22 737,21 740,25 C 743,28 744,308 740,310 C 737,313 513,314 510,310 C 507,307 507,28 510,25 Z" fill="rgba(232,128,114,0.06)" stroke="#e88072" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <circle cx="625" cy="75" r="30" fill="#e88072" opacity="0.9"/>
    <text x="625" y="82" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="white" font-weight="700">5-12 YOE</text>
    <text x="625" y="130" text-anchor="middle" font-family="'Caveat', cursive" font-size="19" fill="#eee0cc" font-weight="700">The Security-</text>
    <text x="625" y="155" text-anchor="middle" font-family="'Caveat', cursive" font-size="19" fill="#eee0cc" font-weight="700">Conscious Lead</text>
    <line x1="545" y1="170" x2="705" y2="170" stroke="#e88072" stroke-width="1" opacity="0.3"/>
    <text x="625" y="200" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#8b949e">"Who threat-modeled</text>
    <text x="625" y="220" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#8b949e">this?"</text>
    <line x1="545" y1="245" x2="705" y2="245" stroke="#e88072" stroke-width="1" opacity="0.3"/>
    <text x="625" y="270" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#4ade80">WTP: $5K–15K</text>
    <text x="625" y="295" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#8b949e">consulting / audit</text>
  </g>
</svg>
</div>

---

## Four Forces of Switching

<div style="display:flex;justify-content:center;margin:16px 0;">
<svg viewBox="0 0 720 420" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:720px;">
  <defs>
    <filter id="roughen-5" x="-2%" y="-2%" width="104%" height="104%">
      <feTurbulence type="turbulence" baseFrequency="0.03" numOctaves="2" result="noise" seed="5"/>
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="1.2" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
    <filter id="glow-5">
      <feGaussianBlur stdDeviation="3" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <marker id="arrow-5" viewBox="0 0 12 10" refX="10" refY="5" markerWidth="8" markerHeight="6" orient="auto-start-reverse" fill="none" stroke="#eee0cc" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
      <path d="M 1,1 L 10,5 L 1,9"/>
    </marker>
  </defs>
  <!-- Quadrant lines -->
  <line x1="360" y1="40" x2="360" y2="340" stroke="#eee0cc" stroke-width="1" opacity="0.2"/>
  <line x1="30" y1="190" x2="690" y2="190" stroke="#eee0cc" stroke-width="1" opacity="0.2"/>
  <!-- Top-left: PUSH -->
  <g filter="url(#roughen-5)" transform="rotate(-0.3, 180, 110)">
    <path d="M 40,50 C 43,47 317,46 320,50 C 323,53 324,168 320,170 C 317,173 43,174 40,170 C 37,167 37,53 40,50 Z" fill="rgba(78,222,128,0.06)" stroke="#4ade80" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="180" y="78" text-anchor="middle" font-family="'Caveat', cursive" font-size="22" fill="#4ade80" font-weight="700">PUSH</text>
    <text x="180" y="105" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#eee0cc">Production incidents</text>
    <text x="180" y="128" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#eee0cc">Mandated adoption</text>
    <text x="180" y="151" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#eee0cc">Career risk</text>
  </g>
  <!-- Top-right: PULL -->
  <g filter="url(#roughen-5)" transform="rotate(0.5, 540, 110)">
    <path d="M 400,50 C 403,47 677,46 680,50 C 683,53 684,168 680,170 C 677,173 403,174 400,170 C 397,167 397,53 400,50 Z" fill="rgba(78,222,128,0.06)" stroke="#4ade80" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="540" y="78" text-anchor="middle" font-family="'Caveat', cursive" font-size="22" fill="#4ade80" font-weight="700">PULL</text>
    <text x="540" y="105" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#eee0cc">Sleep through the night</text>
    <text x="540" y="128" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#eee0cc">Diagnostic capability</text>
    <text x="540" y="151" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#eee0cc">Data-driven decisions</text>
  </g>
  <!-- Bottom-left: ANXIETY (larger) -->
  <g filter="url(#roughen-5)" transform="rotate(0.4, 180, 290)">
    <path d="M 25,210 C 28,207 332,206 335,210 C 338,213 339,348 335,350 C 332,353 28,354 25,350 C 22,347 22,213 25,210 Z" fill="rgba(248,113,113,0.08)" stroke="#f87171" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="180" y="242" text-anchor="middle" font-family="'Caveat', cursive" font-size="24" fill="#f87171" font-weight="700">ANXIETY</text>
    <text x="180" y="272" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc">Trust crisis ("another grifter")</text>
    <text x="180" y="298" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc">"Will it be outdated in 3 mo?"</text>
    <text x="180" y="324" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc">"Show me YOUR production"</text>
  </g>
  <!-- Bottom-right: HABIT -->
  <g filter="url(#roughen-5)" transform="rotate(-0.6, 540, 280)">
    <path d="M 400,215 C 403,212 677,211 680,215 C 683,218 684,338 680,340 C 677,343 403,344 400,340 C 397,337 397,218 400,215 Z" fill="rgba(136,136,136,0.05)" stroke="#888888" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="540" y="245" text-anchor="middle" font-family="'Caveat', cursive" font-size="22" fill="#888888" font-weight="700">HABIT</text>
    <text x="540" y="278" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#8b949e">"I'll figure it from docs"</text>
    <text x="540" y="305" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#8b949e">Status quo is comfortable</text>
    <text x="540" y="328" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#8b949e">No budget approval needed</text>
  </g>
  <!-- Arrow from ANXIETY to callout -->
  <path d="M 335,280 C 380,280 420,395 460,395" stroke="#f87171" stroke-width="2" fill="none" stroke-dasharray="6,4" marker-end="url(#arrow-5a)"/>
  <defs>
    <marker id="arrow-5a" viewBox="0 0 12 10" refX="10" refY="5" markerWidth="8" markerHeight="6" orient="auto-start-reverse" fill="none" stroke="#f87171" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
      <path d="M 1,1 L 10,5 L 1,9"/>
    </marker>
  </defs>
  <g filter="url(#glow-5)">
    <path d="M 460,380 C 463,377 697,376 700,380 C 703,383 704,413 700,415 C 697,418 463,419 460,415 C 457,412 457,383 460,380 Z" fill="rgba(232,128,114,0.15)" stroke="#e88072" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="580" y="403" text-anchor="middle" font-family="'Caveat', cursive" font-size="17" fill="#e88072" font-weight="700">Key unlock: published receipts</text>
  </g>
</svg>
</div>

---

## Two Offers

<div style="display:flex;justify-content:center;margin:16px 0;">
<svg viewBox="0 0 740 360" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:740px;">
  <defs>
    <filter id="roughen-6" x="-2%" y="-2%" width="104%" height="104%">
      <feTurbulence type="turbulence" baseFrequency="0.03" numOctaves="2" result="noise" seed="6"/>
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="1.2" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
  </defs>
  <!-- Card A: Cohort -->
  <g filter="url(#roughen-6)" transform="rotate(-0.5, 185, 190)">
    <path d="M 15,30 C 18,27 352,26 355,30 C 358,33 359,328 355,330 C 352,333 18,334 15,330 C 12,327 12,33 15,30 Z" fill="rgba(232,128,114,0.06)" stroke="#e88072" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="185" y="65" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#8b949e" font-weight="700">OFFER A</text>
    <text x="185" y="95" text-anchor="middle" font-family="'Caveat', cursive" font-size="24" fill="#eee0cc" font-weight="700">Cohort</text>
    <line x1="60" y1="110" x2="310" y2="110" stroke="#e88072" stroke-width="1" opacity="0.3"/>
    <text x="185" y="140" text-anchor="middle" font-family="'Caveat', cursive" font-size="32" fill="#e88072" font-weight="700">$749</text>
    <text x="185" y="162" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#8b949e">founding price ($997 full)</text>
    <line x1="60" y1="178" x2="310" y2="178" stroke="#e88072" stroke-width="1" opacity="0.2"/>
    <text x="185" y="202" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc">4 weeks, live on Maven</text>
    <text x="185" y="226" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc">15–25 seats per cohort</text>
    <text x="185" y="250" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc">OTel + evals + STRIDE</text>
    <line x1="60" y1="270" x2="310" y2="270" stroke="#e88072" stroke-width="1" opacity="0.2"/>
    <text x="185" y="295" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#4ade80">Target: Firefighter + Architect</text>
  </g>
  <!-- Card B: Security -->
  <g filter="url(#roughen-6)" transform="rotate(0.4, 555, 190)">
    <path d="M 385,30 C 388,27 722,26 725,30 C 728,33 729,328 725,330 C 722,333 388,334 385,330 C 382,327 382,33 385,30 Z" fill="rgba(232,128,114,0.06)" stroke="#e88072" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="555" y="65" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#8b949e" font-weight="700">OFFER B</text>
    <text x="555" y="95" text-anchor="middle" font-family="'Caveat', cursive" font-size="24" fill="#eee0cc" font-weight="700">Security Workshop</text>
    <line x1="430" y1="110" x2="680" y2="110" stroke="#e88072" stroke-width="1" opacity="0.3"/>
    <text x="555" y="140" text-anchor="middle" font-family="'Caveat', cursive" font-size="28" fill="#e88072" font-weight="700">$497 + $5K–15K</text>
    <text x="555" y="162" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#8b949e">workshop + audit retainer</text>
    <line x1="430" y1="178" x2="680" y2="178" stroke="#e88072" stroke-width="1" opacity="0.2"/>
    <text x="555" y="202" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc">3-hour deep dive</text>
    <text x="555" y="226" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc">Warm lead: Trilogy cyber</text>
    <text x="555" y="250" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc">STRIDE + 5 PoC exploits</text>
    <line x1="430" y1="270" x2="680" y2="270" stroke="#e88072" stroke-width="1" opacity="0.2"/>
    <text x="555" y="295" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#4ade80">Target: Security-Conscious Lead</text>
  </g>
  <!-- Connecting dashed line -->
  <path d="M 355,180 C 365,180 375,180 385,180" stroke="#eee0cc" stroke-width="1.5" stroke-dasharray="6,4" opacity="0.4"/>
  <text x="370" y="350" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#8b949e">shared infrastructure: articles, audience, credibility</text>
</svg>
</div>

---

## The Curriculum Stack

<div style="display:flex;justify-content:center;margin:16px 0;">
<svg viewBox="0 0 650 420" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:650px;">
  <defs>
    <filter id="roughen-7" x="-2%" y="-2%" width="104%" height="104%">
      <feTurbulence type="turbulence" baseFrequency="0.03" numOctaves="2" result="noise" seed="7"/>
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="1.2" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
    <marker id="arrow-7" viewBox="0 0 12 10" refX="10" refY="5" markerWidth="8" markerHeight="6" orient="auto-start-reverse" fill="none" stroke="#eee0cc" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
      <path d="M 1,1 L 10,5 L 1,9"/>
    </marker>
  </defs>
  <!-- Layer 0: Pre-work (bottom) -->
  <g filter="url(#roughen-7)" transform="rotate(0.3, 360, 370)">
    <path d="M 120,350 C 123,347 597,346 600,350 C 603,353 604,393 600,395 C 597,398 123,399 120,395 C 117,392 117,353 120,350 Z" fill="rgba(136,136,136,0.08)" stroke="#888888" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <circle cx="145" cy="372" r="14" fill="#888888"/>
    <text x="145" y="378" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="white" font-weight="700">0</text>
    <text x="370" y="378" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#888888">Pre-work: Agent Anatomy</text>
  </g>
  <!-- Layer 1: Observability -->
  <g filter="url(#roughen-7)" transform="rotate(-0.5, 360, 295)">
    <path d="M 120,270 C 123,267 597,266 600,270 C 603,273 604,313 600,315 C 597,318 123,319 120,315 C 117,312 117,273 120,270 Z" fill="rgba(232,128,114,0.10)" stroke="#e88072" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <circle cx="145" cy="292" r="14" fill="#e88072"/>
    <text x="145" y="298" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="white" font-weight="700">1</text>
    <!-- Eye icon -->
    <ellipse cx="175" cy="292" rx="10" ry="6" fill="none" stroke="#eee0cc" stroke-width="1.5"/>
    <circle cx="175" cy="292" r="3" fill="#eee0cc"/>
    <text x="370" y="298" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc">Observability — OpenTelemetry</text>
  </g>
  <!-- Layer 2: Testing -->
  <g filter="url(#roughen-7)" transform="rotate(0.4, 360, 215)">
    <path d="M 120,190 C 123,187 597,186 600,190 C 603,193 604,233 600,235 C 597,238 123,239 120,235 C 117,232 117,193 120,190 Z" fill="rgba(232,128,114,0.10)" stroke="#e88072" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <circle cx="145" cy="212" r="14" fill="#e88072"/>
    <text x="145" y="218" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="white" font-weight="700">2</text>
    <!-- Checkmark icon -->
    <path d="M 170,215 L 175,220 L 185,207" fill="none" stroke="#eee0cc" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="370" y="218" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc">Testing — Statistical Evals</text>
  </g>
  <!-- Layer 3: Security -->
  <g filter="url(#roughen-7)" transform="rotate(-0.3, 360, 135)">
    <path d="M 120,110 C 123,107 597,106 600,110 C 603,113 604,153 600,155 C 597,158 123,159 120,155 C 117,152 117,113 120,110 Z" fill="rgba(232,128,114,0.10)" stroke="#e88072" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <circle cx="145" cy="132" r="14" fill="#e88072"/>
    <text x="145" y="138" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="white" font-weight="700">3</text>
    <!-- Shield icon -->
    <path d="M 175,122 L 182,126 L 182,136 C 182,142 175,146 175,146 C 175,146 168,142 168,136 L 168,126 Z" fill="none" stroke="#eee0cc" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="370" y="138" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc">Security — STRIDE Threat Model</text>
  </g>
  <!-- Layer 4: Prove Value / Kill -->
  <g filter="url(#roughen-7)" transform="rotate(0.2, 360, 55)">
    <path d="M 120,30 C 123,27 597,26 600,30 C 603,33 604,73 600,75 C 597,78 123,79 120,75 C 117,72 117,33 120,30 Z" fill="rgba(232,128,114,0.15)" stroke="#e88072" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
    <circle cx="145" cy="52" r="14" fill="#e88072"/>
    <text x="145" y="58" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="white" font-weight="700">4</text>
    <!-- Gauge icon -->
    <circle cx="175" cy="52" r="8" fill="none" stroke="#eee0cc" stroke-width="1.5"/>
    <path d="M 175,52 L 180,46" stroke="#e88072" stroke-width="2" stroke-linecap="round"/>
    <text x="370" y="58" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc">Prove Value or Kill — Ship the Dashboard</text>
  </g>
  <!-- Left arrow: "Build UP" -->
  <path d="M 80,380 C 78,340 78,120 80,50" stroke="#eee0cc" stroke-width="2" fill="none" marker-end="url(#arrow-7)" opacity="0.6"/>
  <text x="60" y="220" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#eee0cc" transform="rotate(-90, 60, 220)" opacity="0.6">Build UP from foundation</text>
</svg>
</div>

---

## Revenue Model

<div style="display:flex;justify-content:center;margin:16px 0;">
<svg viewBox="0 0 720 380" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:720px;">
  <defs>
    <filter id="roughen-8" x="-2%" y="-2%" width="104%" height="104%">
      <feTurbulence type="turbulence" baseFrequency="0.03" numOctaves="2" result="noise" seed="8"/>
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="1.2" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
    <filter id="glow-8">
      <feGaussianBlur stdDeviation="5" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>
  <text x="360" y="30" text-anchor="middle" font-family="'Caveat', cursive" font-size="20" fill="#eee0cc" font-weight="700">Annual Revenue Potential</text>
  <!-- Baseline -->
  <line x1="50" y1="320" x2="700" y2="320" stroke="#eee0cc" stroke-width="1" opacity="0.2"/>
  <!-- Bar 1: Cohort $100K -->
  <g filter="url(#roughen-8)" transform="rotate(-0.3, 120, 200)">
    <path d="M 70,100 C 73,97 167,96 170,100 C 173,103 174,318 170,320 C 167,323 73,324 70,320 C 67,317 67,103 70,100 Z" fill="rgba(78,222,128,0.15)" stroke="#4ade80" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="120" y="85" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#4ade80" font-weight="700">~$100K</text>
    <text x="120" y="350" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#eee0cc">Cohort</text>
    <text x="120" y="368" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#8b949e">4x25x$997</text>
  </g>
  <!-- Bar 2: Enterprise $40K -->
  <g filter="url(#roughen-8)" transform="rotate(0.4, 250, 240)">
    <path d="M 200,190 C 203,187 297,186 300,190 C 303,193 304,318 300,320 C 297,323 203,324 200,320 C 197,317 197,193 200,190 Z" fill="rgba(78,222,128,0.12)" stroke="#4ade80" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="250" y="175" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#4ade80" font-weight="700">$30–50K</text>
    <text x="250" y="350" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#eee0cc">Enterprise</text>
    <text x="250" y="368" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#8b949e">team licenses</text>
  </g>
  <!-- Bar 3: Workshops $30K -->
  <g filter="url(#roughen-8)" transform="rotate(-0.5, 380, 255)">
    <path d="M 330,210 C 333,207 427,206 430,210 C 433,213 434,318 430,320 C 427,323 333,324 330,320 C 327,317 327,213 330,210 Z" fill="rgba(78,222,128,0.10)" stroke="#4ade80" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="380" y="195" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#4ade80" font-weight="700">~$30K</text>
    <text x="380" y="350" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#eee0cc">Workshops</text>
    <text x="380" y="368" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#8b949e">4x$7.5K</text>
  </g>
  <!-- Bar 4: Audits $70K -->
  <g filter="url(#roughen-8)" transform="rotate(0.3, 510, 220)">
    <path d="M 460,155 C 463,152 557,151 560,155 C 563,158 564,318 560,320 C 557,323 463,324 460,320 C 457,317 457,158 460,155 Z" fill="rgba(78,222,128,0.12)" stroke="#4ade80" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="510" y="140" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#4ade80" font-weight="700">$60–80K</text>
    <text x="510" y="350" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#eee0cc">Audits</text>
    <text x="510" y="368" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#8b949e">6-8x$10K</text>
  </g>
  <!-- Total bar: highlighted -->
  <g filter="url(#roughen-8)">
    <g filter="url(#glow-8)">
      <path d="M 610,65 C 613,62 697,61 700,65 C 703,68 704,318 700,320 C 697,323 613,324 610,320 C 607,317 607,68 610,65 Z" fill="rgba(232,128,114,0.18)" stroke="#e88072" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
    </g>
    <text x="655" y="52" text-anchor="middle" font-family="'Caveat', cursive" font-size="20" fill="#e88072" font-weight="700">$220–260K</text>
    <text x="655" y="350" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#e88072" font-weight="700">TOTAL</text>
  </g>
</svg>
</div>

---

## Competitive Map

<div style="display:flex;justify-content:center;margin:16px 0;">
<svg viewBox="0 0 720 440" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:720px;">
  <defs>
    <filter id="roughen-9" x="-2%" y="-2%" width="104%" height="104%">
      <feTurbulence type="turbulence" baseFrequency="0.03" numOctaves="2" result="noise" seed="9"/>
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="1.2" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
    <filter id="glow-9">
      <feGaussianBlur stdDeviation="6" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <marker id="arrow-9" viewBox="0 0 12 10" refX="10" refY="5" markerWidth="8" markerHeight="6" orient="auto-start-reverse" fill="none" stroke="#eee0cc" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
      <path d="M 1,1 L 10,5 L 1,9"/>
    </marker>
  </defs>
  <!-- Axes -->
  <path d="M 100,400 L 680,400" stroke="#eee0cc" stroke-width="1.5" opacity="0.4" marker-end="url(#arrow-9)"/>
  <path d="M 100,400 L 100,30" stroke="#eee0cc" stroke-width="1.5" opacity="0.4" marker-end="url(#arrow-9)"/>
  <text x="400" y="430" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#8b949e">Price →</text>
  <text x="70" y="220" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#8b949e" transform="rotate(-90, 70, 220)">Depth →</text>
  <text x="130" y="420" font-family="'Caveat', cursive" font-size="12" fill="#8b949e">Free</text>
  <text x="650" y="420" font-family="'Caveat', cursive" font-size="12" fill="#8b949e">$2K+</text>
  <text x="105" y="395" font-family="'Caveat', cursive" font-size="12" fill="#8b949e">Intro</text>
  <text x="105" y="55" font-family="'Caveat', cursive" font-size="12" fill="#8b949e">Prod</text>
  <!-- Andrew Ng -->
  <g filter="url(#roughen-9)">
    <circle cx="170" cy="350" r="18" fill="rgba(136,136,136,0.15)" stroke="#888888" stroke-width="1.5"/>
    <text x="170" y="355" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#888888">Ng</text>
    <text x="170" y="380" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#8b949e">$49</text>
  </g>
  <!-- Anthropic Academy -->
  <g filter="url(#roughen-9)">
    <circle cx="140" cy="320" r="16" fill="rgba(136,136,136,0.12)" stroke="#888888" stroke-width="1.5"/>
    <text x="140" y="325" text-anchor="middle" font-family="'Caveat', cursive" font-size="10" fill="#888888">Anth</text>
    <text x="140" y="345" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#8b949e">FREE</text>
  </g>
  <!-- Udemy -->
  <g filter="url(#roughen-9)">
    <circle cx="160" cy="370" r="14" fill="rgba(136,136,136,0.10)" stroke="#888888" stroke-width="1.5"/>
    <text x="195" y="375" font-family="'Caveat', cursive" font-size="11" fill="#8b949e">Udemy $14</text>
  </g>
  <!-- Skool / Liam Ottley -->
  <g filter="url(#roughen-9)">
    <circle cx="310" cy="330" r="18" fill="rgba(136,136,136,0.12)" stroke="#888888" stroke-width="1.5"/>
    <text x="310" y="335" text-anchor="middle" font-family="'Caveat', cursive" font-size="10" fill="#888888">Skool</text>
    <text x="310" y="358" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#8b949e">agency bros</text>
  </g>
  <!-- IndyDevDan -->
  <g filter="url(#roughen-9)">
    <circle cx="370" cy="240" r="18" fill="rgba(136,136,136,0.15)" stroke="#888888" stroke-width="1.5"/>
    <text x="370" y="245" text-anchor="middle" font-family="'Caveat', cursive" font-size="10" fill="#888888">Indy</text>
    <text x="370" y="268" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#8b949e">$599</text>
  </g>
  <!-- AI Makerspace -->
  <g filter="url(#roughen-9)">
    <circle cx="530" cy="210" r="20" fill="rgba(136,136,136,0.15)" stroke="#888888" stroke-width="1.5"/>
    <text x="530" y="206" text-anchor="middle" font-family="'Caveat', cursive" font-size="10" fill="#888888">AI</text>
    <text x="530" y="218" text-anchor="middle" font-family="'Caveat', cursive" font-size="10" fill="#888888">Maker</text>
    <text x="530" y="240" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#8b949e">$1.5-2K</text>
  </g>
  <!-- Hamel Husain -->
  <g filter="url(#roughen-9)">
    <circle cx="430" cy="130" r="18" fill="rgba(136,136,136,0.15)" stroke="#888888" stroke-width="1.5"/>
    <text x="430" y="128" text-anchor="middle" font-family="'Caveat', cursive" font-size="10" fill="#888888">Hamel</text>
    <text x="430" y="140" text-anchor="middle" font-family="'Caveat', cursive" font-size="10" fill="#888888">Husain</text>
    <text x="430" y="158" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#8b949e">owns evals</text>
  </g>
  <!-- US — large, coral, glowing -->
  <g filter="url(#roughen-9)">
    <g filter="url(#glow-9)">
      <circle cx="580" cy="80" r="35" fill="rgba(232,128,114,0.20)" stroke="#e88072" stroke-width="2.5"/>
    </g>
    <text x="580" y="76" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#e88072" font-weight="700">US</text>
    <text x="580" y="94" text-anchor="middle" font-family="'Caveat', cursive" font-size="12" fill="#eee0cc">$749–997</text>
    <text x="580" y="130" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#e88072">Production depth</text>
  </g>
</svg>
</div>

---

## Execution Calendar

<div style="display:flex;justify-content:center;margin:16px 0;">
<svg viewBox="0 0 740 300" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:740px;">
  <defs>
    <filter id="roughen-10" x="-2%" y="-2%" width="104%" height="104%">
      <feTurbulence type="turbulence" baseFrequency="0.03" numOctaves="2" result="noise" seed="10"/>
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="1.2" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
    <filter id="glow-10">
      <feGaussianBlur stdDeviation="4" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>
  <!-- Main timeline -->
  <path d="M 40,130 C 60,131 680,129 720,130" stroke="#eee0cc" stroke-width="2" stroke-dasharray="8,5" opacity="0.4" fill="none" stroke-linecap="round"/>
  <!-- Milestone 1: Mar 8 -->
  <g filter="url(#roughen-10)">
    <circle cx="60" cy="130" r="16" fill="rgba(232,128,114,0.12)" stroke="#e88072" stroke-width="2"/>
    <text x="60" y="135" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#eee0cc">Mar 8</text>
    <text x="60" y="170" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#eee0cc">Publish</text>
    <text x="60" y="188" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#eee0cc">articles</text>
  </g>
  <!-- Milestone 2: Mar 15 -->
  <g filter="url(#roughen-10)">
    <circle cx="160" cy="130" r="16" fill="rgba(232,128,114,0.12)" stroke="#e88072" stroke-width="2"/>
    <text x="160" y="135" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#eee0cc">Mar 15</text>
    <text x="160" y="170" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#eee0cc">LinWheel</text>
    <text x="160" y="188" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#eee0cc">series + repo</text>
  </g>
  <!-- Milestone 3: Mar 22 -->
  <g filter="url(#roughen-10)">
    <circle cx="260" cy="130" r="16" fill="rgba(232,128,114,0.12)" stroke="#e88072" stroke-width="2"/>
    <text x="260" y="135" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#eee0cc">Mar 22</text>
    <text x="260" y="170" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#eee0cc">Workshop</text>
    <text x="260" y="188" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#eee0cc">landing page</text>
  </g>
  <!-- Milestone 4: Mar 29 — coral highlight -->
  <g filter="url(#roughen-10)">
    <circle cx="360" cy="130" r="18" fill="rgba(232,128,114,0.20)" stroke="#e88072" stroke-width="2.5"/>
    <text x="360" y="135" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#eee0cc">Mar 29</text>
    <text x="360" y="170" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#e88072" font-weight="700">Free</text>
    <text x="360" y="188" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#e88072" font-weight="700">workshop</text>
  </g>
  <!-- Milestone 5: Apr 5 — green -->
  <g filter="url(#roughen-10)">
    <circle cx="460" cy="130" r="18" fill="rgba(78,222,128,0.15)" stroke="#4ade80" stroke-width="2.5"/>
    <text x="460" y="135" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#eee0cc">Apr 5</text>
    <text x="460" y="170" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#4ade80" font-weight="700">Presale</text>
    <text x="460" y="188" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#4ade80" font-weight="700">open</text>
  </g>
  <!-- Milestone 6: Apr 14 — RED KILL DECISION -->
  <g filter="url(#roughen-10)">
    <g filter="url(#glow-10)">
      <circle cx="560" cy="130" r="22" fill="rgba(248,113,113,0.20)" stroke="#f87171" stroke-width="3"/>
    </g>
    <text x="560" y="128" text-anchor="middle" font-family="'Caveat', cursive" font-size="12" fill="#f87171" font-weight="700">Apr 14</text>
    <text x="560" y="143" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#f87171">KILL?</text>
    <text x="560" y="80" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#f87171" font-weight="700">KILL DECISION</text>
    <path d="M 560,95 L 560,107" stroke="#f87171" stroke-width="2" stroke-dasharray="4,3"/>
  </g>
  <!-- Milestone 7: Apr 21–May 18 — green bar -->
  <g filter="url(#roughen-10)">
    <path d="M 640,115 C 643,112 717,111 720,115 C 723,118 724,148 720,150 C 717,153 643,154 640,150 C 637,147 637,118 640,115 Z" fill="rgba(78,222,128,0.15)" stroke="#4ade80" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <text x="680" y="137" text-anchor="middle" font-family="'Caveat', cursive" font-size="12" fill="#4ade80" font-weight="700">Cohort 1</text>
    <text x="680" y="170" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#8b949e">Apr 21</text>
    <text x="680" y="185" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#8b949e">– May 18</text>
  </g>
  <!-- Bottom labels -->
  <text x="390" y="250" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc" opacity="0.6">6 weeks: signal → ship → kill-or-scale</text>
</svg>
</div>

---

## Kill Criteria

<div style="display:flex;justify-content:center;margin:16px 0;">
<svg viewBox="0 0 720 350" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:720px;">
  <defs>
    <filter id="roughen-11" x="-2%" y="-2%" width="104%" height="104%">
      <feTurbulence type="turbulence" baseFrequency="0.03" numOctaves="2" result="noise" seed="11"/>
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="1.2" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
  </defs>
  <!-- Gate 1 -->
  <g filter="url(#roughen-11)" transform="rotate(-0.5, 140, 160)">
    <path d="M 50,40 C 53,37 227,36 230,40 C 233,43 234,278 230,280 C 227,283 53,284 50,280 C 47,277 47,43 50,40 Z" fill="rgba(232,128,114,0.04)" stroke="#eee0cc" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <!-- Gate bar -->
    <path d="M 70,160 L 210,160" stroke="#e88072" stroke-width="3" stroke-linecap="round" stroke-dasharray="8,4" opacity="0.8"/>
    <text x="140" y="70" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc" font-weight="700">Gate 1</text>
    <text x="140" y="95" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#8b949e">Week 1</text>
    <!-- Threshold -->
    <text x="140" y="140" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#e88072">< 5 enrollments</text>
    <text x="140" y="200" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#eee0cc">→ contingency</text>
    <!-- Status light -->
    <circle cx="140" cy="245" r="16" fill="rgba(232,128,114,0.3)" stroke="#e88072" stroke-width="2"/>
    <text x="140" y="250" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#e88072">YELLOW</text>
  </g>
  <!-- Gate 2 -->
  <g filter="url(#roughen-11)" transform="rotate(0.3, 380, 160)">
    <path d="M 280,40 C 283,37 477,36 480,40 C 483,43 484,278 480,280 C 477,283 283,284 280,280 C 277,277 277,43 280,40 Z" fill="rgba(248,113,113,0.04)" stroke="#f87171" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <path d="M 300,160 L 460,160" stroke="#f87171" stroke-width="3" stroke-linecap="round" stroke-dasharray="8,4" opacity="0.8"/>
    <text x="380" y="70" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc" font-weight="700">Gate 2</text>
    <text x="380" y="95" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#8b949e">Month 1</text>
    <text x="380" y="140" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#f87171">< 15 enrollments</text>
    <text x="380" y="200" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#f87171" font-weight="700">→ KILL cohort</text>
    <circle cx="380" cy="245" r="16" fill="rgba(248,113,113,0.3)" stroke="#f87171" stroke-width="2"/>
    <text x="380" y="250" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#f87171">RED</text>
  </g>
  <!-- Gate 3 -->
  <g filter="url(#roughen-11)" transform="rotate(-0.4, 610, 160)">
    <path d="M 510,40 C 513,37 707,36 710,40 C 713,43 714,278 710,280 C 707,283 513,284 510,280 C 507,277 507,43 510,40 Z" fill="rgba(248,113,113,0.04)" stroke="#f87171" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <path d="M 530,160 L 690,160" stroke="#f87171" stroke-width="3" stroke-linecap="round" stroke-dasharray="8,4" opacity="0.8"/>
    <text x="610" y="70" text-anchor="middle" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc" font-weight="700">Gate 3</text>
    <text x="610" y="95" text-anchor="middle" font-family="'Caveat', cursive" font-size="14" fill="#8b949e">Month 3</text>
    <text x="610" y="140" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#f87171">< $15K revenue</text>
    <text x="610" y="200" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#f87171" font-weight="700">→ KILL business line</text>
    <circle cx="610" cy="245" r="16" fill="rgba(248,113,113,0.3)" stroke="#f87171" stroke-width="2"/>
    <text x="610" y="250" text-anchor="middle" font-family="'Caveat', cursive" font-size="11" fill="#f87171">RED</text>
  </g>
  <!-- Pivot note -->
  <text x="360" y="325" text-anchor="middle" font-family="'Caveat', cursive" font-size="15" fill="#8b949e">Pivot trigger: enterprise demand > individual → enterprise-first model</text>
</svg>
</div>

---

## Bias Check

<div style="display:flex;justify-content:center;margin:16px 0;">
<svg viewBox="0 0 700 320" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:700px;">
  <defs>
    <filter id="roughen-12" x="-2%" y="-2%" width="104%" height="104%">
      <feTurbulence type="turbulence" baseFrequency="0.03" numOctaves="2" result="noise" seed="12"/>
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="1.2" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
  </defs>
  <!-- Dashboard frame -->
  <g filter="url(#roughen-12)">
    <path d="M 30,20 C 33,17 667,16 670,20 C 673,23 674,268 670,270 C 667,273 33,274 30,270 C 27,267 27,23 30,20 Z" fill="rgba(232,128,114,0.03)" stroke="#eee0cc" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" opacity="0.4"/>
  </g>
  <!-- Indicator 1: Confirmation Bias — YELLOW -->
  <g filter="url(#roughen-12)" transform="rotate(-0.3, 180, 80)">
    <circle cx="100" cy="80" r="22" fill="rgba(250,204,21,0.25)" stroke="#facc15" stroke-width="2.5"/>
    <text x="100" y="86" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#facc15" font-weight="700">WARN</text>
    <text x="260" y="72" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc" font-weight="700">Confirmation Bias</text>
    <text x="260" y="95" font-family="'Caveat', cursive" font-size="14" fill="#8b949e">Excitement may inflate perceived edge</text>
  </g>
  <!-- Indicator 2: Availability Bias — GREEN -->
  <g filter="url(#roughen-12)" transform="rotate(0.2, 180, 145)">
    <circle cx="100" cy="145" r="22" fill="rgba(78,222,128,0.25)" stroke="#4ade80" stroke-width="2.5"/>
    <text x="100" y="151" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#4ade80" font-weight="700">PASS</text>
    <text x="260" y="137" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc" font-weight="700">Availability Bias</text>
    <text x="260" y="160" font-family="'Caveat', cursive" font-size="14" fill="#8b949e">Independent data confirmation (5+ sources)</text>
  </g>
  <!-- Indicator 3: Anchoring — GREEN -->
  <g filter="url(#roughen-12)" transform="rotate(-0.4, 180, 210)">
    <circle cx="100" cy="210" r="22" fill="rgba(78,222,128,0.25)" stroke="#4ade80" stroke-width="2.5"/>
    <text x="100" y="216" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#4ade80" font-weight="700">PASS</text>
    <text x="260" y="202" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc" font-weight="700">Anchoring</text>
    <text x="260" y="225" font-family="'Caveat', cursive" font-size="14" fill="#8b949e">SDP re-scoring maintained original ranking</text>
  </g>
  <!-- Indicator 4: Excitement Bias — RED -->
  <g filter="url(#roughen-12)" transform="rotate(0.3, 180, 250)">
    <circle cx="100" cy="250" r="22" fill="rgba(248,113,113,0.25)" stroke="#f87171" stroke-width="2.5"/>
    <text x="100" y="256" text-anchor="middle" font-family="'Caveat', cursive" font-size="13" fill="#f87171" font-weight="700">FLAG</text>
    <text x="260" y="242" font-family="'Caveat', cursive" font-size="18" fill="#eee0cc" font-weight="700">Excitement Bias</text>
    <text x="260" y="265" font-family="'Caveat', cursive" font-size="14" fill="#f87171">"Publish first, workshop second" — correct ordering matters</text>
  </g>
  <!-- Bottom note -->
  <text x="350" y="305" text-anchor="middle" font-family="'Caveat', cursive" font-size="16" fill="#eee0cc" opacity="0.7">Evidence is private. Publishing is the prerequisite, not a nice-to-have.</text>
</svg>
</div>

---

## What We Have (Receipts)

<div class="grid grid-cols-2 gap-8 mt-4">
<div>

### <span class="green">Verified</span>

- Princeton CS, edX Principal ($60MM+ ARR), AWS SA
- qortex, bilrost, Vindler, qortex-observe, cadence
- STRIDE threat model + 5 PoC exploits
- 20+ Agent Skills (buildlog extraction)
- This entire validation pipeline

</div>
<div>

### <span class="red">Still Needed</span>

- Published articles (15 drafts in queue)
- Published STRIDE findings
- 30 days learning-loop data
- Course-specific audience (0 today)
- Testimonials (pre-launch = zero)

</div>
</div>

---
layout: center
---

## The Ask

<p class="stat-big">3 articles by April 1.</p>

<p class="stat-big" style="font-size:2.2rem;">Workshop by April 15.</p>

<p class="stat-big" style="font-size:2.2rem;">15 presale students or kill.</p>

<br/>

<p class="text-lg mt-4">Review the landing page on Vercel preview</p>
<p class="text-lg">Review the full pitch deck in the Obsidian vault</p>

<p class="muted text-sm mt-8">Every number in this deck traces back to a signal scan, decision log, or persona extract.</p>

---

## Appendix — Asset Map

| Artifact | Location |
|---|---|
| Signal Scan | `Signal-Scans/production-agent-engineering.md` |
| Decision Log | `Decisions/production-agent-engineering.md` |
| Persona Extract | `Personas/production-agent-engineering.md` |
| Offer Scope | `Offers/production-agent-engineering.md` |
| Pitch | `Pitches/production-agent-engineering.md` |
| Content Seeds | `Content-Briefs/*.md` |
| Landing Page | `launchpad/index.html` (Vercel preview) |
| This Deck | `launchpad/deck/slides.md` |
| Kanban | Obsidian vault — Product-Discovery board |
| PR | `github.com/Peleke/launchpad` — `production-agent-engineering` |

<p class="muted text-sm mt-4">All artifacts generated by the hunter pipeline: signal-scan → decision-log → persona-extract → offer-scope → pitch → assets</p>

---
layout: center
---

<p class="text-2xl" style="color:#eee0cc;">Built with the hunter pipeline.</p>

<p class="muted mt-4">signal-scan → decision-log → persona-extract → offer-scope → pitch → assets</p>

<p class="muted text-sm mt-8">2026-03-05</p>
