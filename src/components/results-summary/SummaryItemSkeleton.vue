<template>
  <li class="summary__list-item">
    <div class="summary-item summary-item--skeleton">
      <div class="summary-item__label">
        <div class="sk sk--icon"></div>
        <div class="sk sk--text"></div>
      </div>

      <div class="summary-item__score">
        <div class="sk sk--score"></div>
      </div>
    </div>
  </li>
</template>

<style scoped>
.summary-item--skeleton {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px;
  border-radius: 12px;
  background: #f3f4fd;
}

.summary-item__label {
  display: flex;
  align-items: center;
  gap: 12px;
}

.sk {
  border-radius: 8px;
  background: linear-gradient(
    90deg,
    rgba(0,0,0,0.06) 25%,
    rgba(0,0,0,0.12) 37%,
    rgba(0,0,0,0.06) 63%
  );
  background-size: 400% 100%;
  animation: shimmer 1.2s ease-in-out infinite;
}

.sk--icon { width: 20px; height: 20px; border-radius: 6px; }
.sk--text { width: 110px; height: 24px; }
.sk--score { width: 70px; height: 24px; }

@keyframes shimmer {
  0% { background-position: 100% 0; }
  100% { background-position: 0 0; }
}
</style>
