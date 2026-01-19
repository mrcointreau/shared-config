<template>
  <div class="slidev-layout two-cols-header w-full h-full text-left">
    <div class="col-header">
      <slot />
    </div>
    <div class="col-left">
      <slot name="left" />
    </div>
    <div class="col-right">
      <slot name="right" />
    </div>
    <div class="col-bottom">
      <slot name="bottom" />
    </div>
  </div>
</template>

<style scoped>
.two-cols-header {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: auto 1fr;
  column-gap: 1.5rem;
  row-gap: 0.75rem;
}

.col-header {
  grid-area: 1 / 1 / 2 / 3;
  margin-bottom: 0.5rem;
}

.col-left {
  grid-area: 2 / 1 / 3 / 2;
}

.col-right {
  grid-area: 2 / 2 / 3 / 3;
}

.col-bottom {
  align-self: end;
  grid-area: 3 / 1 / 3 / 3;
}

.two-cols-header h1 + p {
  color: #6b7280;
}

.col-left > * + *,
.col-right > * + * {
  margin-top: 1rem;
}


.two-cols-header :deep(th:last-child),
.two-cols-header :deep(td:last-child) {
  border-right: none;
}
</style>
