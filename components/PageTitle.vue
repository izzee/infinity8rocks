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

<style lang="scss" scoped>
  @keyframes marquee {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }

  @keyframes marquee-left {
    from { transform: translateX(-50%); }
    to { transform: translateX(0%); }
  }

  .page-title {
    @include s(top);
    position: sticky;
    display: flex;
    overflow: hidden;
    text-align: center;
  }
  .title-marquee {
    display: flex;
    @include s(gap);
    align-items: center;
    animation: marquee 60s infinite linear;
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