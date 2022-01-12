<template>
  <div>
      <div class="buttons">
      <button v-on:click="showSection(1)"  v-bind:class="{active:knapp==1}">Section-1</button>
      <button v-on:click="showSection(2)"  v-bind:class="{active:knapp==2}">Section-2</button>
      <button v-on:click="showSection(3)" v-bind:class="{active:knapp==3}">Section-3</button>
      </div>
      <section v-if="knapp==1">Section-1 text :::Lorem ipsum dolor sit amet consectetur adipisicing elit. Amet maiores accusamus similique aliquam laudantium at suscipit ab consectetur, 
          quas perspiciatis a voluptate, enim ea vel? Eaque deserunt voluptatem veritatis tenetur.</section>
      <section v-else-if="knapp==2">Section-2 text :::Lorem ipsum dolor sit amet consectetur adipisicing elit. Amet maiores accusamus similique aliquam laudantium at suscipit ab consectetur, 
          quas perspiciatis a voluptate, enim ea vel? Eaque deserunt voluptatem veritatis tenetur.</section>
      <section v-else-if="knapp==3">Section-3 text :::Lorem ipsum dolor sit amet consectetur adipisicing elit. Amet maiores accusamus similique aliquam laudantium at suscipit ab consectetur, 
          quas perspiciatis a voluptate, enim ea vel? Eaque deserunt voluptatem veritatis tenetur.</section>
  </div>
</template>

<script>
export default {
  data(){return{
      knapp:0
  }},

  methods:{
      showSection(number){
          this.knapp=number
      }
  }

}
</script>

<style>
 .buttons{
     display:flex;
 }
 .buttons button{
     padding: 5px;
     margin: 5px;
 }
 .button-1{
     background-color: rgb(153, 137, 137);
 }
 .active{
     background-color: seagreen;
 }
</style>