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
  background-color: #F7FAFC;
}

.layout-interactive::after {
  content: '';
  position: absolute;
  inset: 30px;
  border: 2px solid rgba(236, 0, 0, 0.15);
  border-radius: 20px;
  animation: pulse-border 3s ease-in-out infinite;
  pointer-events: none;
}

@keyframes pulse-border {
  0%, 100% {
    border-color: rgba(236, 0, 0, 0.15);
    box-shadow: 0 0 0 0 rgba(236, 0, 0, 0);
  }
  50% {
    border-color: rgba(236, 0, 0, 0.4);
    box-shadow: 0 0 25px rgba(236, 0, 0, 0.1);
  }
}

.interactive-icon {
  font-size: 2.5em;
  margin-bottom: 0.3em;
  opacity: 0.4;
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
  font-size: 0.8em;
  color: #718096;
  letter-spacing: 0.1em;
  text-transform: uppercase;
}
</style>
