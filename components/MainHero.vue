<template>
  <div class="main-hero" @click="() => changeImage(1)">
    <!-- <nuxt-img src="images/dancing-cats-edit.gif" /> -->
    <nuxt-img 
      v-for="(image, index) in images"
      :key="index"
      :src="`images/${image}`"
      :class="activeImg === index && `active`"
    />

  </div>
</template>

<script>
export default {
  data() {
    return {
      activeImg: 0,
      images: [
        'dancing-cats-edit.gif',
        'catgifangel.gif',
        'glitched-logo.gif',
      ]
    }
  },
  methods: {
    changeImage(direction) {
      let nextImg = this.activeImg + direction;
      let imgLength = this.images.length;
      if (nextImg === imgLength){
        nextImg = 0
      } else if(nextImg === -1){
        nextImg = imgLength -1
      } 
      this.activeImg = nextImg
      console.log(this.activeImg)
    }
  }
}
</script>

<style>

</style>


<style scoped lang="scss">
.main-hero{
  // border: 4px solid $skyblue;
  overflow: hidden;
  @include rounded;
  width: 100%;
  position: relative;
  // max-height: 100vw;
  // height: 100%;
    flex: 1;
  @include bp(lg){

  }

  img {
    @include bp(lg) {
      position: absolute;
    }
    
    height:100%;
    width:100%;
    transition: opacity 3s;
    object-fit: fill;
  }
  img:not(.active) {
    opacity: 0;
  }
}
</style>