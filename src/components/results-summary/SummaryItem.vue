<script setup>
import { computed } from 'vue'

const props = defineProps({
  title: String,
  icon: String,
  value: Number
})

const themeClass = computed(() => {
  return `summary-item--${props.title.toLowerCase()}`
})
</script>

<template>
  <li class="summary__list-item">
    <div class="summary-item" :class="themeClass">
      <div class="summary-item__label">
        <img :src="icon" class="summary-item__icon">
        <span class="summary-item__name">{{ title }}</span>
      </div>
      <div class="summary-item__score">
        <span class="summary-item__value">{{ value }}</span>
        <span class="summary-item__divider">/</span>
        <span class="summary-item__total">100</span>
      </div>
    </div>
  </li>

</template>

<style lang="scss" scoped>
  .summary-item {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px;
    border-radius: 12px;

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

  .summary-item--reaction {
    background-color: var(--red-50);

    .summary-item__name {
      color: var(--red-400);
    }
  }

  .summary-item--memory {
    background-color: var(--yellow-50);

    .summary-item__name {
      color: var(--yellow-400);
    }
  }

  .summary-item--verbal {
    background-color: var(--green-50);

    .summary-item__name {
      color: var(--green-500);
    }
  }

  .summary-item--visual {
    background-color: var(--blue-50);

    .summary-item__name {
      color: var(--navy-800);
    }
  }
</style>
