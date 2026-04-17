<template>
  <div class="layout-section">
    <div class="section-content">
      <slot />
    </div>
  </div>
</template>

<style>
.layout-section {
  background: linear-gradient(135deg, #EC0000, #C00000);
  color: #FFFFFF;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  height: 100%;
  position: relative;
}

.section-content {
  position: relative;
  z-index: 1;
}

.section-content h1 {
  color: #FFFFFF !important;
  font-size: 2.5em !important;
}

.section-content p {
  color: rgba(255, 255, 255, 0.85);
  font-size: 1.2em;
}

.section-content strong {
  color: #FFFFFF;
}
</style>
