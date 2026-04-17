<template>
  <div class="progress-bar">
    <div class="progress-label">Lab {{ current }} de {{ total }}</div>
    <div class="progress-track">
      <div class="progress-fill" :style="{ width: (current / total * 100) + '%' }"></div>
    </div>
    <div class="progress-steps">
      <div
        v-for="i in total"
        :key="i"
        class="progress-step"
        :class="{ active: i <= current, current: i === current }"
      >
        {{ i }}
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  current: { type: Number, default: 1 },
  total: { type: Number, default: 4 }
})
</script>

<style scoped>
.progress-bar {
  padding: 1em 0;
}

.progress-label {
  font-size: 0.75em;
  color: #718096;
  margin-bottom: 0.5em;
  text-transform: uppercase;
  letter-spacing: 0.1em;
}

.progress-track {
  height: 4px;
  background: rgba(236, 0, 0, 0.1);
  border-radius: 2px;
  overflow: hidden;
  margin-bottom: 0.8em;
}

.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, #EC0000, #C00000);
  border-radius: 2px;
  transition: width 0.5s ease;
}

.progress-steps {
  display: flex;
  justify-content: space-between;
}

.progress-step {
  width: 28px;
  height: 28px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.75em;
  font-weight: 600;
  background: #F7FAFC;
  color: #718096;
  border: 2px solid rgba(236, 0, 0, 0.15);
}

.progress-step.active {
  background: #EC0000;
  color: #FFFFFF;
  border-color: #EC0000;
}

.progress-step.current {
  box-shadow: 0 0 10px rgba(236, 0, 0, 0.3);
}
</style>
