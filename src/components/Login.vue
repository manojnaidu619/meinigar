<template lang="html">
  <div class="container">
    <h1>Hello World!</h1>
    <div v-if="output" class="output">
      <table>
        <tr>
          <th><h3>ID</h3></th>
          <th><h3>User</h3></th>
          <th><h3>Password</h3></th>
        </tr>
        <tr v-for="data in output.data">
          <td>{{data["ID"]}}</td>
          <td>{{data["UserName"]}}</td>
          <td>{{data["Password"]}}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data(){
    return{
      output: ''
    }
  },
  created(){
    axios.get('https://fakerestapi.azurewebsites.net/api/Users')
    .then(res => {this.output = res
      var response = res.data
          for(var i=0;i<response.length;i++){
            localStorage.setItem(`User ${i+1}`, [response[i]["UserName"], response[i]["Password"]])
          }
    })
    .catch(error => console.log(error));
  }
}
</script>

<style lang="css" scoped>
.output{
  margin-left: 42%;
  margin-top: 20px;
}
 table,th,td{
   border: 1px solid black;
   border-collapse: collapse;
   padding: 5px;
 }
</style>
