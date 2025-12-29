<script setup>

</script>

<template>
  <main class="main">
    <slot/>
  </main>
</template>

<style lang="scss" scoped>
  .main {
    display: flex;
    align-items: center;
    flex: 1;
    justify-content: center;

    @media (min-width: 768px) {
      padding: 40px;
    }
  }
</style>
