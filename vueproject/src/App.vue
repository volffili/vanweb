<template>
  <div class="center">
    <img alt="Vue logo" src="./assets/logo.png">
    <div class="calendarWrapper">
      <Calendar/>
    </div>
  </div>
</template>

<script>
import Calendar from './components/Calendar.vue'

export default {
  name: 'App',
  components: {
    Calendar
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.center {
  margin: auto;
  max-width: 1024px;
}
.calendarWrapper{
  width: 100%;
  height: 600px;
}
</style>
