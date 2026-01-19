<script setup>
  import { computed } from 'vue'

  const props = defineProps({
    items: {
      type: Array,
      required: true
    },
    loading: { 
      type: Boolean, 
      default: false 
    }
  })

  const totalValue = computed(() => {
    const sum = props.items.reduce((acc, item) => acc + item.score, 0)
    return Math.round(sum / props.items.length)
  })
</script>

<template>
  <div class="score-panel">
    <h1 class="score-panel__title">Your Result</h1>
    <div class="score-panel__circle">
      <div class="score-panel__score">
        <p class="score-panel__value">{{ loading ? '--' : totalValue }}</p>
        <p class="score-panel__total">of 100</p>
      </div>
    </div>
    <div class="score-panel__message">
      <p class="score-panel__grade">Great</p>
      <p class="score-panel__description">
        You scored higher than 65%&nbsp;of the people who have taken these tests.
      </p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
 .score-panel {
  display: flex;
  flex-direction: column;
  width: 100%;
  padding: 32px;
  justify-content: center;
  align-items: center;
  gap: 24px;
  background: var(--gradient-2);
  color: var(--navy-200);
  text-align: center;
  border-radius: 0 0 32px 32px;

  @media (min-width: 768px) {
    min-width: 338px;
    max-width: 368px;
    gap: 32px;
    padding: 45px 54px;
    border-radius: 32px;
  }

  &__title {
    @include text-preset-5;

    @media (min-width: 768px) {
      @include text-preset-4;
    }
  }

  &__circle {
    display: flex;
    width: 140px;
    height: 140px;
    justify-content: center;
    align-items: center;
    border-radius: 50%;
    background: var(--gradient-1);

    @media (min-width: 768px) {
      width: 200px;
      height: 200px;
    }
  }

  &__value {
    @include text-preset-2;
    color: var(--white);

    @media (min-width: 768px) {
      @include text-preset-1;
    }
  }

  &__total {
    @include text-preset-6;
    opacity: 0.5;

    @media (min-width: 768px) {
      @include text-preset-5;
    }
  }

  &__grade {
    @include text-preset-4;
    color: var(--white);

    @media (min-width: 768px) {
      @include text-preset-3;
    }
  }

  &__description {
    @include text-preset-6--medium;
    margin-top: 8px;

    @media (min-width: 768px) {
      @include text-preset-5--medium;
      margin-top: 16px;
    }
  }
 }
</style>
