<template>

  <myapp />
</template>

<script>
import myapp from './components/myapp.vue'

export default {
  name: 'App',
  components: {
    myapp
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
  font-family: IS;
}

body{
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: #161623;
    font-family: IS !important;
}
body::before{
    content: '';
    position: absolute;
    top: 0;
    right: 0;
    width: 100vh;
    height: 100vh;
    background: linear-gradient(#f00,#f0f);
    clip-path: circle(45% at right 80%);
}
body::after{
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100vh;
    height: 100vh;
    background: linear-gradient(#2196f3,#e61e63);
    clip-path: circle(20% at 10% 10%);
}
</style>

