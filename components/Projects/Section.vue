<template>
  <section>
    <h2 class="section-title" v-html="project.title"/>
    <div class="section-body">
      <p v-html="project.text"/>
      <p v-html="project.images"/>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    title: String,
    text: String,
    images: Array,
    project: Object,
  }
}
</script>

<style lang="scss" scoped>
  section {
    background-color: $white;
    border-radius: 24px;

    @include s(margin-top);

    overflow: hidden;
    @include bp(md) {
      border-radius: 32px;
    }
  }
  .section-title {
    padding: 8px;

    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1), inset 0px 2px 8px #A7A7A7, inset 0px -2px 8px #A7A7A7;
    background: linear-gradient(180deg, #FFFFFF 0%, #c3c3c3 100%);
    text-align: center;
    font-size: 16px;
    line-height: 2;
    font-weight: 400;
    border-top-right-radius: 24px;
    border-top-left-radius: 24px;
    @include bp(md) {
      font-size: 24px;
      border-top-right-radius: 32px;
      border-top-left-radius: 32px;
    }
  }

  .section-body {
    padding: 24px;
    min-height: calc(100vh - 400px);
  }
</style>