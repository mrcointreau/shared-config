<template>
  <div class="slidev-layout center-list">
    <div class="center-list__inner">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.center-list {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

.center-list__inner {
  width: min(900px, 100%);
  display: flex;
  flex-direction: column;
  align-items: center;
}

.center-list__inner h1,
.center-list__inner h2,
.center-list__inner h3,
.center-list__inner p {
  text-align: center;
}

.center-list__inner h1 + p {
  color: #6b7280;
}

.center-list__inner ul,
.center-list__inner ol {
  align-self: center;
  width: min(700px, 100%);
  margin: 0.75rem 0 0;
  padding-left: 1.25rem;
  list-style-position: outside;
  text-align: left !important;
}

.center-list__inner li,
.center-list__inner li > p {
  text-align: left !important;
}
</style>
