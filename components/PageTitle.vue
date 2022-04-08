<template>
  <a href="#" class="page-title green-border">
    <div class="title-marquee">
      <nuxt-img src="images/infinity.svg"/>
      <h1>Infinity</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Rocks</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Infinity</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Rocks</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Infinity</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Rocks</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Infinity</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Rocks</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Infinity</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Rocks</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Infinity</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Rocks</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Infinity</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Rocks</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Infinity</h1>
      <nuxt-img src="images/infinity.svg"/>
      <h1>Rocks</h1>
    </div>
  </a>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
  @keyframes marquee {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }

  .page-title {
    text-align: center;


    overflow: hidden;
    display: flex;
      position: sticky;
      top: 16px;



    @include bp(md) {
      top: 24px;
    }
  }

  .title-marquee {
    display: flex;
    @include s(gap);
    align-items: center;
    animation: marquee 30s infinite linear;
    h1 {
      text-transform: uppercase;
      color: $skyblue;
      font-size: 16px;
      line-height: 2;
    }
    img {
      height: 12px;
    }


    @include bp(xs) {
      h1 {

        font-size: 24px;
      }
      img {
        height: 16px;
      }

    }

    @include bp(md) {

      h1 {
        font-size: 40px;
        line-height: 1.6;
      }

      img {
        height: 32px;
      }
    }
  }



</style>