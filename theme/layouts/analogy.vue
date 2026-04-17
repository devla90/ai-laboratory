<template>
  <div class="layout-analogy-wrapper">
    <div class="analogy-visual">
      <slot name="visual" />
    </div>
    <div class="analogy-text">
      <slot />
    </div>
  </div>
</template>

<style>
.layout-analogy-wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2.5em;
  height: 100%;
  padding: 2em 2.5em;
  align-items: center;
  background-color: #F7FAFC;
}

.analogy-visual {
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, rgba(236, 0, 0, 0.05), rgba(236, 0, 0, 0.02));
  border-radius: 16px;
  padding: 2em;
  min-height: 280px;
}

.analogy-visual img {
  max-width: 100%;
  max-height: 280px;
  border-radius: 12px;
}

.analogy-visual .emoji-large {
  font-size: 6em;
}

.analogy-text h2 {
  color: #C00000 !important;
  margin-bottom: 0.5em;
  font-size: 1.4em;
}

.analogy-text ul {
  list-style: none;
  padding: 0;
}

.analogy-text ul li {
  padding: 0.4em 0;
  padding-left: 1.5em;
  position: relative;
  font-size: 0.95em;
  line-height: 1.5;
}

.analogy-text ul li::before {
  content: '▸';
  color: #EC0000;
  position: absolute;
  left: 0;
  font-weight: bold;
}
</style>
