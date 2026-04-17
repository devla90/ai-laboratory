<template>
  <div class="layout-comparison-wrapper">
    <div class="comparison-header">
      <slot name="header" />
    </div>
    <div class="comparison-body">
      <slot />
    </div>
  </div>
</template>

<style>
.layout-comparison-wrapper {
  display: flex;
  flex-direction: column;
  height: 100%;
  padding: 2em 2.5em;
  background-color: #F7FAFC;
}

.comparison-header {
  margin-bottom: 1.5em;
}

.comparison-header h1 {
  font-size: 1.8em !important;
}

.comparison-body {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
</style>
