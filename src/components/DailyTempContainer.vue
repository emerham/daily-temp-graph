<template>
  <div v-for="dailyTemp in dailyTemps" :key="dailyTemp.datetimeEpoch">
    <daily-temp-item
      :date="getDateString(dailyTemp.datetime)"
      :high="dailyTemp.tempmax"
      :color-class="getColorClassFromTemp(dailyTemp.tempmax)"
    />
  </div>
</template>

<script>
import DailyTempItem from "@/components/DailyTempItem.vue";
import dailyTempData from "@/assets/daily_temperature.json";
import dateAp from "ap-style-date";

export default {
  name: "DailyTempContainer",
  components: {
    DailyTempItem,
  },
  methods: {
    getDateString(date) {
      return dateAp.longAP(date);
    },
    getColorClassFromTemp(temp) {
      let roundedTens = Math.floor(temp / 10) * 10;
      if (roundedTens < 20) {
        return "Twenty";
      } else if (roundedTens > 120) {
        return "HundoTwenty";
      }
      switch (roundedTens) {
        case 20:
          return "Twenty";
        case 30:
          return "Thirty";
        case 40:
          return "Forty";
        case 50:
          return "Fifty";
        case 60:
          return "Sixty";
        case 70:
          return "Seventy";
        case 80:
          return "Eighty";
        case 90:
          return "Ninety";
        case 100:
          return "Hundo";
        case 110:
          return "Hundoten";
        case 120:
          return "HundoTwenty";
      }
    },
  },
  data() {
    return {
      dailyTemps: dailyTempData.days,
    };
  },
};
</script>
