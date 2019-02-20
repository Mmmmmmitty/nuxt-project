<template>
  <div>
    <h1 class="title">HELLO WORLD</h1>
    <nuxt-link :to="{name:'asyncData'}">asyncData</nuxt-link>
    <nuxt-link :to="{name:'about'}">about</nuxt-link>
    <nuxt-link :to="{name:'news',params:{newsId:3306}}">news</nuxt-link>
    <h1>ES6 promise</h1>
    <p>{{firstStep}}</p>
    <p>{{secondStep}}</p>
    <p>{{thirdStep}}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      status: 1,
      firstStep: "",
      secondStep: "",
      thirdStep: ""
    };
  },
  created() {
    let self = this;
    // new Promise(self.step1).then(function(data) {
    //   self.firstStep = data;
    //   new Promise(self.step2).then(function(data) {
    //     self.secondStep = data;
    //     new Promise(self.step3).then(function(data) {
    //       self.thirdStep = data;
    //     });
    //   });
    // });
    new Promise(self.step1)
      .then(function(data) {
        console.log(data)
        self.firstStep = data;
        return new Promise(self.step2);
      })
      .then(function(data) {
        console.log(data)
        self.secondStep = data;
        return new Promise(self.step3);
      })
      .then(function(data) {
        console.log(data)
        self.thirdStep = data;
      });
  },
  methods: {
    step1(resolve, reject) {
      if (this.status == 1) {
        resolve("第一步完成");
      } else {
        reject("第一步失败");
      }
    },
    step2(resolve, reject) {
      if (this.status == 1) {
        resolve("第二步完成");
      } else {
        reject("第二步失败");
      }
    },
    step3(resolve, reject) {
      if (this.status == 1) {
        resolve("第三步完成");
      } else {
        reject("第三步失败");
      }
    }
  }
};
</script>

<style scoped>
</style>

