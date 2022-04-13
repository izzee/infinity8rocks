<template>
  <div class="page-content">
    <MainHero/>
  </div>
</template>

<script>
export default {
  // middleware: [
  //   function({ redirect }) {
  //     redirect('/projects');
  //   },
  // ],
  head() {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }],
    };
  },
};

</script>

<style scoped lang="scss">
  .page-content {
    display: flex;
    flex: 1;
  }
</style>