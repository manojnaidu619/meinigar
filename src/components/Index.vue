<template lang="html">
  <div class="container">
    <h1>Welome!</h1>
    <div class="login-modal">
      <label for="email">Email </label>
      <input type="text" name="email" value="" v-model="email"><br><br>
      <label for="password">Password </label>
      <input type="password" name="password" value="" v-model="password"><br><br>
      <button class="submit" :disabled="!validated" type="submit" name="button">Submit</button>
    </div>
    <div class="login-button">
      <button id="login" type="button" name="button">Login</button>
    </div>
    <div class="signup-button">
      <button id="signup" type="button" name="button">Signup</button>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
        email: '',
        password: '',
        validated: false
    }
  },
  computed:{
      signale(){
        var mailformat = /\S+@\S+\.\S+/
        if(this.email.match(mailformat)) {
          this.validated = true
        }
      }
  }
}
</script>

<style lang="css" scoped>
  .login-button, .signup-button{
    margin: 150px;
  }
  button{
    height: 50px;
    background-color: orange;
    border: none;
    border-radius: 3px;
    width: 120px;
    outline: none;
    text-align: center;
    font-style: bold;
    font-size: 23px;
    cursor: pointer;
    box-shadow: 5px 5px 10px darkgray;
    transition: 0.3s linear;
  }
  button:hover{
    background-color: darkorange;
    transform: scale(0.9);
    box-shadow: none;
  }
  .submit{
    transform: scale(0.7);
  }
  .login-modal{
    height: 100%;
    width: 500px;
    padding: 15px;
    border: 1px solid red;
  }
  [disabled]{
    box-shadow: none;
    cursor: not-allowed;
    transform: none;
  }
</style>
