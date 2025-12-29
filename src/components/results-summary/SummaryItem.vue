<script setup>

</script>

<template>
  <div class="summary-item">
    <div class="summary-item__label">
      <img src="/icons/icon-reaction.svg" class="summary-item__icon">
      <span class="summary-item__name">Reaction</span>
    </div>
    <div class="summary-item__score">
      <span class="summary-item__value">80</span>
      <span class="summary-item__divider">/</span>
      <span class="summary-item__total">100</span>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .summary-item {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px;
    border-radius: 12px;
    background-color: var(--red-50);

    &__label {
      display: flex;
      gap: 14px;
      align-items: center;
    }

    &__icon {
      width: 20px;
      height: 20px;
    }

    &__name {
      @include text-preset-6--medium;
      color: var(--red-400);

      @media (min-width: 768px) {
        @include text-preset-5--medium;
      }
    }

    &__score {
      display: flex;
      gap: 8px;
    }

    &__value {
      @include text-preset-6;
      color: var(--navy-950);

      @media (min-width: 768px) {
        @include text-preset-5;
      }
    }

    &__divider,
    &__total {
      @include text-preset-6;
      color: var(--navy-950);
      opacity: 0.5;

      @media (min-width: 768px) {
        @include text-preset-5;
      }
    }
  }
</style>
