<template>
  <main>
    <h1>Feed</h1>
    <div class="feed">
      <nuxt-link 
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
      </nuxt-link>
    </div>
  </main>
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
.post {
  display: block;
  margin-top: 16px;

  img {
    width: 100%;
  }
  .post-info {
    display: flex;
    justify-content: space-between;
  }

  a {
    text-decoration: none;
  }
}
</style>