<template>
  <div>
    <h2>News-Content [{{$route.params.id}}]</h2>
    <ul>
      <li>
        <nuxt-link :to="{name:'index'}">home</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  validate({ params }) {
    // Must be a number
    return /^\d+$/.test(params.id);
  },
};
</script>

<style scoped>
</style>
