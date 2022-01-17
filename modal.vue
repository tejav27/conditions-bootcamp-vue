<template>
  <div>
      <div class="wrapper">
    <div class="main-view" v-bind:class="{fadeView:modal}">
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatum 
        aque culpa corporis possimus? Libero, exercitationem. Possimus, consectetur veniam laboriosam deserunt nobis sunt fugiat sequi odit pariatur suscipit officiis aliquam molestias.</p>
      <button v-on:click="showModal">Send</button>
    </div>
    <div v-bind:class="{modalView:modal}" v-if="modal">
        <p>Your message has been sent</p>
        <button v-on:click="modal=false">Back</button>
    </div>
      </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      modal: "",
    };
  },
  methods: {
    showModal() {
      this.modal = true;
    },
  },
};
</script>

<style>

*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
.wrapper{
  position: relative;
  width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;  
    height: 100vh;
    transition: 0.5s;
    padding: 20px;
}
.main-view{
  position : relative;
    height: 300px;
    width: 300px;
    border: black solid 2px;
    display: flex;
    padding: 20px;
    margin: 20px;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.fadeView{
    opacity: 0.4;
}
.modalView{
  position: absolute;
  top: 20%;
  left: 80%;
  transform: translate(-50%,-50%);
    z-index: 2;
    display: flex;
    height: 200px;
    width: 150px;
    border:rgb(96, 187, 88) solid 3px;
    justify-content: center;
    align-items: center;
    position: static;
    top: 5px;
}
</style>