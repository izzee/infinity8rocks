<template>
  <div class="main-hero">
    <nuxt-img src="images/dancing-cats-edit.gif" />
  </div>
</template>

<script>
export default {

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
  @include bp(lg){

    flex: 1;
  }

  img {
    @include bp(lg) {
      position: absolute;
    }
    height:100%;
    width:100%;
  }
}
</style>