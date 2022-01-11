<template>
  <div>
      <div class="wrapper">
    <div class="main-view" v-bind:class="{fadeView:modal}">
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
.wrapper{
    display: flex;
    justify-content: center;
    align-items: center;  
    height: 100vh;
}
.main-view{
    height: 300px;
    width: 300px;
    border: black solid 2px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.fadeView{
    opacity: 0.4;
}
.modalView{
    z-index: 2;
    display: flex;
    height: 200px;
    width: 150px;
    border:blue solid 3px;
    justify-content: center;
    align-items: center;
    position: static;
    top: 5px;
}
</style>