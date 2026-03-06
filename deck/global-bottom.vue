<template>
  <div class="slide-footer">
    <span class="footer-confidential">CONFIDENTIAL</span>
    <img src="/endstation-logo.png" class="footer-logo" alt="endstation" />
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
  height: 18px;
  width: auto;
  opacity: 0.18;
  filter: brightness(1.2);
}
</style>
