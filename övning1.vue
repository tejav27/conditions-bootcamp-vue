<template>
  <div>
      <img src="../condition-bootcamp/låda.jpg" alt="låda">
      <h1 v-if="random==1">Frontend utvecklare</h1>
      <h1 v-else-if="random==2">Backend utvecklare</h1>
      <button v-on:click="showName">Click Me!!</button>
  </div>
</template>

<script>
export default {
    data(){return{
        random: 0
    }},
    methods:{
        showName(){
            this.random= Math.ceil(Math.random()*2)
        }
    }
}
</script>

<style>

</style>