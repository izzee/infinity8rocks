<template>
  <div class="site-nav">
    <nuxt-link class="hero green-border" to="/" exact>
      <nuxt-img src="images/infinity-rock-video.gif"/>
    </nuxt-link>
    <nav class="site-links green-border">
      <nuxt-link to="/projects">Projects</nuxt-link>
      <nuxt-link to="/about">About</nuxt-link>
      <nuxt-link to="/feed">Feed</nuxt-link>
    </nav>
  </div>
</template>

<style scoped lang="scss">

  @keyframes pulse {
    from {
      transform: scale(1);
      filter: blur(0);
      opacity: 1;
    }
    to {
      transform: scale(.75);
      filter: blur(4px);
      opacity: .6;
    }
  }
  @keyframes blur {
    from {
      filter: blur(1px);
    }
    to {
      filter: blur(2vw);
    }
  }

  .site-nav {
    display: flex;
    flex-direction: column-reverse;
    @include s(gap);

    
    @include bp(md) {
      flex-direction: row;
      & > * {
        padding: 8px;
      }
    }
    @include bp(lg) {
      position: sticky;
      top: 24px;
      left: 24px;
      height: calc(100vh - 48px);
      flex-direction: column;
    }
  }

  .hero {
    width: 100%;
    height: 100%;
    max-height: 50vh;
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    overflow: hidden;
    background-color: $green;
    @include bp(md) {
      flex: 1;
      width: 50%;
      height: 50%;
    }
    @include bp(lg) {
      width: 320px;
      max-height: 320px;
    }
    img {
      width: 100%;
      height: 100%;
      max-height: 50vh;
      object-fit: contain;
      animation: pulse 4s infinite alternate-reverse;
    }
  }

  nav {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    @include s(gap);

    a {
      display: block;
      color: $skyblue;
      font-size: 16px;
      line-height: 2;
      font-weight: 700;
      text-transform: uppercase;
      &:hover,
      &.active,
      &.nuxt-link-active,
      &.nuxt-link-exact-active {
        color: $yellow;
      }
    }

    @include bp(xs) {
      a {
        font-size: 24px;
        line-height: 2;
      }
    }

    @include bp(md) {
      flex-direction: column;
      a {
        font-size: 40px;
        line-height: 1;
      }
    }
  }
</style>