<template>
  <div :class="['w-100', 'px-3', 'py-2', 'text-center', colorClass]">
    <span class="fw-bolder fs-3">{{ date }}, {{ high }} F</span>
  </div>
</template>

<script>
export default {
  name: "DailyTempItem",
  props: {
    date: String,
    high: Number,
    unit: String,
    colorClass: String,
  },
};
</script>
