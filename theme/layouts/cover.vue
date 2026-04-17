<template>
  <div class="layout-cover">
    <div class="corner-decoration top-left"></div>
    <div class="corner-decoration bottom-right"></div>
    <div class="cover-content">
      <slot />
    </div>
    <div class="lab-indicator" v-if="$attrs.labNumber">
      Lab {{ $attrs.labNumber }}
    </div>
  </div>
</template>

<style>
.layout-cover {
  background: linear-gradient(135deg, #1a1a2e, #16213e);
  color: #FFFFFF;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  height: 100%;
  position: relative;
  overflow: hidden;
}

.layout-cover::after {
  content: '';
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(236, 0, 0, 0.06) 1px, transparent 1px),
    linear-gradient(90deg, rgba(236, 0, 0, 0.06) 1px, transparent 1px);
  background-size: 30px 30px;
  pointer-events: none;
}

.layout-cover::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 500px;
  height: 500px;
  transform: translate(-50%, -50%);
  background: radial-gradient(circle, rgba(236, 0, 0, 0.15), transparent 70%);
  pointer-events: none;
}

.cover-content {
  position: relative;
  z-index: 1;
  max-width: 80%;
}

.cover-content h1 {
  color: #FFFFFF !important;
  text-shadow: 0 0 40px rgba(236, 0, 0, 0.5) !important;
  font-size: 2.8em !important;
  margin-bottom: 0.2em;
}

.cover-content h2 {
  color: rgba(255, 255, 255, 0.75) !important;
  font-weight: 400;
  font-size: 1.4em;
}

.cover-content p {
  color: rgba(255, 255, 255, 0.5);
  font-size: 1em;
}

.corner-decoration {
  position: absolute;
  width: 60px;
  height: 60px;
  border: 2px solid rgba(236, 0, 0, 0.3);
  z-index: 1;
}

.corner-decoration.top-left {
  top: 24px;
  left: 24px;
  border-right: none;
  border-bottom: none;
}

.corner-decoration.bottom-right {
  bottom: 24px;
  right: 24px;
  border-left: none;
  border-top: none;
}

.lab-indicator {
  position: absolute;
  bottom: 30px;
  left: 50%;
  transform: translateX(-50%);
  font-size: 0.85em;
  color: rgba(236, 0, 0, 0.6);
  letter-spacing: 0.2em;
  text-transform: uppercase;
  z-index: 1;
}
</style>
