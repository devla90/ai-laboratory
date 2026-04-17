<template>
  <div class="layout-interactive">
    <div class="interactive-icon">💬</div>
    <div class="interactive-content">
      <slot />
    </div>
    <div class="interactive-hint">Pregunta abierta al equipo</div>
  </div>
</template>

<style>
.layout-interactive {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  height: 100%;
  padding: 3em;
  position: relative;
  background-color: #FFFFFF;
}

.layout-interactive::after {
  content: '';
  position: absolute;
  inset: 40px;
  border: 1px solid rgba(236, 0, 0, 0.12);
  border-radius: 16px;
  pointer-events: none;
}

.interactive-icon {
  font-size: 2.5em;
  margin-bottom: 0.3em;
  opacity: 0.35;
}

.interactive-content {
  position: relative;
  z-index: 1;
  max-width: 75%;
}

.interactive-content h1 {
  font-size: 2.2em !important;
  line-height: 1.3;
  color: #EC0000 !important;
}

.interactive-hint {
  position: absolute;
  bottom: 40px;
  font-size: 0.75em;
  color: #718096;
  letter-spacing: 0.15em;
  text-transform: uppercase;
}
</style>
