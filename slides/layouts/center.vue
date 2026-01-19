<template>
  <div class="slidev-layout center">
    <div class="center__inner">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.center {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  text-align: center;
}

.center__inner {
  width: min(900px, 100%);
}

.center__inner h1 + p {
  color: #6b7280;
}

.center__inner > div {
  margin-top: 1.5rem;
  font-size: 1.1em;
}
</style>
