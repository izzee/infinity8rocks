<template>
  <section>
    <h2 class="section-title" v-html="project.title"/>
    <div class="section-body">
      <p v-html="project.text"/>
      <div :class="`project-images ${project.carousel && 'carousel'}`">
        <nuxt-img 
          v-for="(image, index) in project.images"
          :key="index"
          :src="`images/projects/${image}`"
          :class="project.carousel && activeImg === index && `active ${index}`"
        />
      </div>
      <div v-if="project.carousel" class="carousel-btns">
        <button 
          class="prev-btn"
          @click="() => {changeImage(-1)}">
          <nuxt-img src="images/arrow.svg"/>
        </button>
        <button 
          class="next-btn"
          @click="() => {changeImage(1)}">
          <nuxt-img src="images/arrow.svg"/>
        </button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    project: Object,
  },

  data() {
    return {
      activeImg: 0
    }
  },
  methods: {
    changeImage(direction) {
      let nextImg = this.activeImg + direction;
      let imgLength = this.project.images.length;
      if (nextImg === imgLength){
        nextImg = 0
      } else if(nextImg === -1){
        nextImg = imgLength -1
      } 
      this.activeImg = nextImg
    }
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
    background: linear-gradient(180deg, $white 0%, #c3c3c3 100%);
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
    @include s(gap);
    @include s(padding);
    display: flex;
    flex-direction: column;
    img {
      width: 100%;
      margin: auto;
      @include bp(md) { 
        width: calc(100% - 96px);
      }
    }
    
    a {
      color: $blue;
    }

    .carousel {
      position: relative;
      border: 1px solid white;
      z-index: 0;
      min-height: calc(100vw - 64px);
      @include bp(md){
        min-height: 400px;
        max-height: 50vh;
      }

      img {
        z-index: -1;
        position: absolute;
        height: 100%;
        object-fit: contain;
        left: 0;
        right: 0;
        top: 0;
      }
      img:not(.active) {
        opacity: 0;
      }
    }

    .carousel-btns {
      display: flex;
      justify-content: center;
      @include s(gap);
      button {
        @include s(height);
        @include s(width);

        box-sizing: content-box;
        padding: 8px;
        display: inline-flex;
        justify-content: flex-end;
        border-radius: 100%;
        -webkit-appearance: none;
        border: 0;
        box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1), inset 0px 2px 8px #A7A7A7, inset 0px -2px 8px #A7A7A7;
        transition: box-shadow .25s;
        cursor: pointer;

        &.prev-btn {
          transform: rotate(180deg);
        }
        img {
          @include s(height);
          width: auto;
          margin: 0;
          @include bp(sm){
            opacity: .3;
            transition: opacity .25s;
          }
        }

        &:hover {
          @include bp(sm) {
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1), inset 0px 2px 8px #717070, inset 0px -2px 8px #A7A7A7;
            img {
              opacity: 1;
            }
          }
        }
      }
    }
  }
</style>