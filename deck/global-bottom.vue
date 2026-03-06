<template>
  <div class="slide-footer">
    <span class="footer-confidential">CONFIDENTIAL</span>
    <span class="footer-logo">endstation</span>
  </div>
</template>

<style scoped>
.slide-footer {
  position: fixed;
  bottom: 14px;
  left: 0;
  right: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 28px;
  pointer-events: none;
  z-index: 10;
}
.footer-confidential {
  font-family: 'Inter', sans-serif;
  font-size: 9px;
  letter-spacing: 0.18em;
  color: rgba(238,224,204,0.12);
  text-transform: uppercase;
  font-weight: 500;
}
.footer-logo {
  font-family: 'Fira Code', monospace;
  font-size: 10px;
  color: rgba(77,207,201,0.18);
  letter-spacing: 0.08em;
  font-weight: 400;
}
</style>
