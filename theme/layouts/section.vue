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

.layout-section::after {
  content: '';
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(255, 255, 255, 0.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.05) 1px, transparent 1px);
  background-size: 40px 40px;
  pointer-events: none;
}

.section-content {
  position: relative;
  z-index: 1;
}

.section-content h1 {
  color: #FFFFFF !important;
  text-shadow: 0 0 30px rgba(0, 0, 0, 0.3) !important;
  font-size: 2.5em !important;
}

.section-content p {
  color: rgba(255, 255, 255, 0.85);
  font-size: 1.2em;
}
</style>
