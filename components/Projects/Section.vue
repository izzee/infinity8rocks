<template>
  <section>
    <h2 class="section-title" v-html="project.title"/>
    <div class="section-body">
      <p v-html="project.text"/>
      <nuxt-img 
        v-for="(image, index) in project.images"
        :key="index"
        :src="`images/projects/${image}`"
      />
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
    @include rounded;
    background-color: $white;
    overflow: hidden;
    & + section {
      @include s(margin-top);
    }
  }
  .section-title {
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1), inset 0px 2px 8px #A7A7A7, inset 0px -2px 8px #A7A7A7;
    background: linear-gradient(180deg, #FFFFFF 0%, #c3c3c3 100%);
    text-align: center;
    font-size: 16px;
    line-height: 2;
    font-weight: 400;
    border-top-right-radius: 16px;
    border-top-left-radius: 16px;
    @include bp(xs) {
      padding: 8px;
      border-top-right-radius: 24px;
      border-top-left-radius: 24px;
    }
    @include bp(md) {
      font-size: 24px;
      border-top-right-radius: 32px;
      border-top-left-radius: 32px;
    }
  }
  .section-body {
    text-align: center;

    @include s(padding);
    display: flex;
    flex-direction: column;
    @include s(gap);
    min-height: calc(100vh - 400px);

    img {
      width: 100%;
      margin: auto;
      box-shadow: 0 0 64px #00000011;
      @include rounded;
      @include bp(md) {
        width: calc(100% - 96px);
      }

    }
    

    a {
      color: $blue;
    }
  }
</style>