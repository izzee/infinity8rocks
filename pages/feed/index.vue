<template>
  <div class="page-content">
    <SharedWindow
      title="Feed"
      class="feed"
    >
      <div 
        class="post"
        v-for="post in posts"
        :key="post.slug"
        :to="post.path"
      >
        <div class="post-info">
          <nuxt-img 
            :src="post.avatar"
            width="80px"
            height="80px"

          />
          <p v-html="post.author" />
          <p v-html="formatDate(post.createdAt)" />
        </div>
        <div class="post-content">
          <p v-html="post.body" />
        </div>
      </div>
    </SharedWindow>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const posts = await $content('feed').fetch()
    console.log(posts)
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
  .page-content {
    flex:1;
    display: flex;
    @include bp(sm) {
      max-height: calc(100vh - 136px);
    }
  }

  .feed {
    flex: 1;
    max-height: 100%;
    overflow-y: scroll;
  }
  .post {
    display: flex;
    flex-direction: column;
    align-items: start;
    @include s(gap);
    .post-content {
      border-top-left-radius: 0;
    }
    @include bp(sm) {
      flex-direction: row;
    }
  }

  .post-info {
    display: flex;
    justify-content: end;
    align-items: end;
    gap: 8px;
    @include bp(sm) {
      gap: 0;
      flex-direction: column;
      align-items: center;
    }
    // flex-direction: column;
    // align-items: start;
  }

  .post-content {
    @include rounded;
    flex: 1;
    text-align: left;
    background-color: $blue;
    box-shadow: 0px 4px 10px #00000044, inset 0px -2px 8px #00000099;
    p { 
      font-size: 24px; 
      padding: 24px;
      color: white;
    }
    
  }
</style>