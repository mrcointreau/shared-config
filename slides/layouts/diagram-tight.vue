<template>
  <div class="slidev-layout diagram-tight">
    <div class="diagram-tight__inner">
      <slot />
    </div>
    <div class="diagram-tight__caption">
      <slot name="caption" />
    </div>
  </div>
</template>

<style scoped>
.diagram-tight {
  display: flex;
  flex-direction: column;
  height: 100%;
  gap: 0.25rem;
}

.diagram-tight__inner {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  flex: 1;
}

.diagram-tight__inner :deep(h1) {
  align-self: flex-start;
  width: 100%;
}

.diagram-tight__caption {
  text-align: center;
  font-size: 0.95em;
}

.diagram-tight h1 + p {
  color: #6b7280;
}
</style>
