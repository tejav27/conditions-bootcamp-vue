<template>
  <div>
    <label for="input">Enter User Name</label>
    <input type="text" v-model="usernameEntered" placeholder="Username" />
    <label for="input">Enter password</label>
    <input type="password" v-model="passwordEntered" placeholder="Password" />
    <button v-on:click="validate()">Send</button>
    <button>{{ status }}</button>
    <section v-if="success == 1">
      <h1>Hemlig vy</h1>
      <p>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit magnam
        accusamus sit tenetur provident blanditiis repudiandae, iure deleniti
        necessitatibus illum dolor eos expedita consectetur?
      </p>
    </section>
    <section v-else-if="success == 2">
      <h1>Error!!!</h1>
      <p>Username and password does not match</p>
    </section>
  </div>
</template>

<script>
export default {
 data(){return{
     usernameV: 'Myname',
     passwordEntered:'',
     usernameEntered:'',
     passwordV: 'secret!',
     success:0,
     status: 'Log In'
 }},
 mounted(){
     if(localStorage.usernameV){
        this.usernameEntered = localStorage.usernameV,
        this.passwordEntered = localStorage.passwordV,
        this.status='Log Out'
     } 
 },
 methods:{
     validate(){
         if(this.usernameV==this.usernameEntered && this.passwordV==this.passwordEntered){
             this.success= 1,
             this.status = 'Log Out',
             localStorage.usernameV = this.usernameV,
             localStorage.passwordV = this.passwordV
         }
         else {
             this.success=2,
             this.status = 'Sign Up'
         }
     }
 }
}
</script>

<style>
</style>

