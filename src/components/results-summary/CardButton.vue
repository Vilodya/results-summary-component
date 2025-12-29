<script setup>

</script>

<template>
  <button class="button">Continue</button>
</template>

<style lang="scss" scoped>
  .button {
    @include text-preset-5;
    width: 100%;
    padding: 17px;
    text-align: center;
    color: var(--white);
    background: var(--navy-950);
    border-radius: 128px;
    cursor: pointer;

    &:focus {
      outline: 0;
    }
    
    &:focus-visible,
    &:hover {
      background: var(--gradient-2);
    }
  }
</style>
