<template>
<main>
  <h1 v-html="post.title"/>
  <nuxt-img :src="post.image"/>
</main>

</template>

<script>
  export default {
    async asyncData({ $content, params }) {
      const post = await $content('feed', params.slug).fetch()
      return { post }
    }
  }
</script>

<style lang="scss" scoped>
img {
  margin-top: 16px;
  width: 100%;
}
</style>
