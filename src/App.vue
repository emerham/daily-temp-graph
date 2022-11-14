<script setup>
import DailyTempContainer from "@/components/DailyTempContainer.vue";
</script>

<template>
  <header class="navbar navbar-dark bg-dark">
    <a class="navbar-brand p-2" href="#"> Daily High temperature blanket </a>
  </header>
  <div class="container">
    <div class="row">
      <main class="col-12">
        <h1>Daily Temp</h1>
        <DailyTempContainer/>
      </main>
    </div>
  </div>
</template>
