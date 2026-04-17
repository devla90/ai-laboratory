<template>
  <div class="question-card">
    <div class="question-icon">{{ icon || '🤔' }}</div>
    <div class="question-text">
      <slot />
    </div>
  </div>
</template>

<script setup>
defineProps({
  icon: { type: String, default: '🤔' }
})
</script>

<style scoped>
.question-card {
  background: rgba(255, 255, 255, 0.95);
  border: 2px solid rgba(236, 0, 0, 0.2);
  border-radius: 16px;
  padding: 2em;
  text-align: center;
  box-shadow: 0 8px 30px rgba(236, 0, 0, 0.08);
  max-width: 600px;
  margin: 0 auto;
}

.question-icon {
  font-size: 2.5em;
  margin-bottom: 0.3em;
}

.question-text {
  font-size: 1.3em;
  color: #2D3748;
  line-height: 1.4;
}
</style>
