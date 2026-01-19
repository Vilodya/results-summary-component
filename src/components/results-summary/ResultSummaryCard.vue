<script setup>
import { ref, onMounted } from 'vue'

import CardButton from './CardButton.vue'
import ResultScorePanel from './ResultScorePanel.vue'
import SummaryItem from './SummaryItem.vue'
import SummaryItemSkeleton from './SummaryItemSkeleton.vue'

import summaryDataJson from '@/data/data.json'

const isLoading = ref(true)
const summaryData = ref([])

onMounted(() => {
  setTimeout(() => {
    summaryData.value = summaryDataJson
    isLoading.value = false
  }, 1200)
})
</script>

<template>
  <div class="card">
    <ResultScorePanel :items="summaryData" :loading="isLoading" />
    <div class="summary">
      <h2 class="summary__title">Summary</h2>
      <ul class="summary__list">
        <!-- skeleton -->
        <template v-if="isLoading">
          <SummaryItemSkeleton v-for="n in 4" :key="n" />
        </template>

        <!-- real data -->
        <template v-else>
          <SummaryItem
            v-for="item in summaryData"
            :key="item.category"
            :title="item.category"
            :value="item.score"
            :icon="item.icon"
          />
        </template>
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

    &__list {
      display: flex;
      flex-direction: column;
      gap: 16px;
    }
  }
</style>
