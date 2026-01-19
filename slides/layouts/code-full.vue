<template>
  <div class="slidev-layout code-full">
    <div class="code-full__inner">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.code-full {
  display: flex;
  justify-content: center;
  height: 100%;
}

.code-full__inner {
  width: min(1000px, 100%);
}

.code-full__inner > * + * {
  margin-top: 1rem;
}

.code-full__inner h1 + p {
  color: #6b7280;
}

.code-full__inner pre {
  margin: 0.5rem 0;
}


.code-full__inner :deep(th:last-child),
.code-full__inner :deep(td:last-child) {
  border-right: none;
}

</style>
