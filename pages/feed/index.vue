<template>
  <div class="page-content">
    <!-- <nuxt-link 
      class="post"
      v-for="post in posts"
      :key="post.slug"
      :to="post.path"
    >
      <nuxt-img 
        :src="post.image" 
      />
      <div class="post-info">
        <p v-html="post.title" />
        <p v-html="formatDate(post.createdAt)" />
      </div>
    </nuxt-link> -->
  </div>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const posts = await $content('feed').fetch()
    return {
      posts
    }
  },
  methods: {
    formatDate(date) {
      const rawDate = new Date(date)
      return rawDate.toLocaleDateString();
    }
  }
}
</script>

<style scoped lang="scss">
</style>