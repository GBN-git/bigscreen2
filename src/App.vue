<template>
  <div class="bigscreen">
    <div class="row">
      <header>
        <h1>天气监测</h1>
      </header>
      <weather></weather>
      <so></so>
    </div>
  </div>
</template>

<script>
import weather from "./components/weather";
import so from "./components/so";
export default {
  components:{weather,so}
}
</script>

<style >
body{
  background-image: url("./assets/bg.png");
}

h1{
  text-align: center;
  color: aliceblue;
  /*background-image: url("./assets/head.png");*/
}
</style>
