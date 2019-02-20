<template>
  <div>
    <h1>asyncData</h1>
    <h4>name:{{info.name}}</h4>
    <h4>age:{{info.age}}</h4>
    <h4>interest:{{info.interest}}</h4>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {};
  },
  async asyncData(){
    let {data} = await axios.get("https://api.myjson.com/bins/dlo7m")
    return {
      info:data
    }
  }
  // asyncData() {
  //   return axios.get("https://api.myjson.com/bins/dlo7m").then(res => {
  //     return {
  //       info: res.data
  //     };
  //   });
  // }
};
</script>

<style>
</style>
