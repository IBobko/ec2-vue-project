<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Here you can find statistics for many areas. You can create your own statistical analysis and share it. <br/>
      Let's make objective statistics available to everybody.


      <img src="http://ec2-18-218-65-252.us-east-2.compute.amazonaws.com:8080/"/>
    </p>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted() {
    console.log("hello.");
    axios.get("http://ec2-18-218-65-252.us-east-2.compute.amazonaws.com:5000").then(function (data){
      console.log(data);
    });




  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
