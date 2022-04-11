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



  .site-nav {
    z-index: 100;
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
    cursor: none;

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
      animation: pulse 16s infinite alternate-reverse;
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
      text-transform: uppercase;
      position: relative;
      transition: color .5s;
      user-select: none;

      @include f1;

      &:after {
        content: "";
        position: absolute;
        left: 50%;
        top: 50%;
        width: 120%;
        height: 60%;
        border-radius: 100%;
        opacity: 0;
        z-index: -1;
        filter: blur(8px);
        transform: translate(-50%, -50%);
        transition: opacity .5s;
        @include bp(md) {
          height: 80%;

          min-width: 160px;
          filter: blur(12px);
        }
      }
      &:nth-child(1):after {
        background-color: $pink;
      }
      &:nth-child(2):after {
        background-color: $yellow;
        }
      &:nth-child(3):after {
        background-color: $blue;
      }
      &:hover,
      &.active,
      &.nuxt-link-active,
      &.nuxt-link-exact-active {
        &:nth-child(1) {
          color: $yellow; 
        }
        &:nth-child(2) {
          color: $blue; 
          }
        &:nth-child(3) {
          color: $pink; 
        }
      }
      &.nuxt-link-active,
      &.nuxt-link-exact-active {
        &:after {
          opacity: 1;
        }
      }
    }

    @include bp(md) {
      flex-direction: column;
    }
  }
</style>