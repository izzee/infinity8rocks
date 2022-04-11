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
    user-select: none;
    cursor: none;
    z-index: 200;
  }
  .title-marquee {
    display: flex;
    @include s(gap);
    align-items: center;
    animation: marquee 60s infinite linear;
    h1 {
      color: $skyblue;
      @include f1;
    }
    img {
      height: 12px;
    }
    @include bp(xs) {
      img {
        height: 16px;
      }
    }
    @include bp(md) {
      img {
        height: 32px;
      }
    }
  }
</style>