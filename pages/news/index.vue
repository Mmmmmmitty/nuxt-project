<template>
  <div>
    <h1>newsId{{$route.params.newsId}}</h1>
    <nuxt-link :to="{name:'index'}">home</nuxt-link>
    <ul>
      <li>
        <nuxt-link :to="{name:'news-id',params:{id:123}}">News-1</nuxt-link>
      </li>
      <li>
        <nuxt-link :to="{name:'news-id',params:{id:456}}">News-2</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  head(){
    return {
      title:'新闻',
      meta: [{hid: 'description', name: 'news', content: '我是新闻'}]
    }
  },
  data() {
    return {};
  }
};
</script>

<style scoped>
</style>
