<template>
  <div class="slidev-layout cover">
    <div class="cover__inner">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.cover {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  text-align: center;
}

.cover__inner {
  width: min(960px, 100%);
}

.cover__inner h1 + p {
  color: #6b7280;
}

.cover__inner div {
  margin-top: 1.5rem;
}

.cover__inner span {
  display: inline-block;
  padding: 0.25rem 0.5rem;
}
</style>
