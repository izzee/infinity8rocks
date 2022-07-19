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
    max-height: calc(100vh - 136px);
  }

  .feed {
    flex: 1;
    max-height: 100%;
    overflow-y: scroll;
  }
  .post {
    display: flex;
    flex-direction: column;;
    gap: 24px;
    .post-content {
      border-top-left-radius: 0;
    }
    @include bp(sm) {
      flex-direction: row;
    //   &:nth-child(even) .post-content {
    //     order: -1;
    //     border-top-right-radius: 0;
    //   }
    }
  }

  .post-info {
    width: 80px;
    height: 80px;
    background-color: #eee;
  }

  .post-content {
    @include rounded;
    flex: 1;
    // border: 1px solid blue;
    text-align: left;
    // border: 1px solid red;
    background-color: $blue;
    box-shadow: 0px 4px 10px #00000044, inset 0px -2px 8px #00000099;
    p { font-size: 24px; }
    color: white;
    padding: 16px;
    
  }
</style>