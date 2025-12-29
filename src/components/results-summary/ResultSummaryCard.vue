<script setup>
import CardButton from './CardButton.vue';
import ResultScorePanel from './ResultScorePanel.vue';
</script>

<template>
  <div class="card">
    <ResultScorePanel />
    <div class="summary">
      <h2 class="summary__title">Summary</h2>
      <ul class="summary__list">
        <li class="summary__list-item"></li>
      </ul>
      <CardButton />
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .card {
    background-color: #ffffff;
    overflow: hidden;
    width: 100%;

    @media (min-width: 768px) {
      display: flex;
      border-radius: 32px;
      max-width: 736px;
    }
  }

  .summary {
    display: flex;
    flex-direction: column;
    flex: 1;
    gap: 24px;
    padding: 24px 30px 30px;

    @media (min-width: 768px) {
      min-width: 348px;
      gap: 32px;
      padding: 45px 40px;
    }

    &__title {
      @include text-preset-5;

      @media (min-width: 768px) {
        @include text-preset-4;
      }
    }
  }
</style>
