<template>
  <div id="cursor">
    <nuxt-img src="images/fx/static.gif"/>
  </div>
</template>

<script>
export default {
  mounted() {
    this.addMouseListener()
  },
  methods: {
    addMouseListener(){
      const cursor = document.querySelector('#cursor')
      const cursorRadius = cursor.getBoundingClientRect().width / 2;
      window.addEventListener('mousemove', () => this.moveCursor(event, cursor, cursorRadius));
    },
    moveCursor(e, cursor, cursorRadius){
      document.body.style.cursor = 'none';
      cursor.style.opacity = '1'
      cursor.style.transform = `translate3d(${e.clientX - cursorRadius}px, ${e.clientY - cursorRadius}px, 0)`;
    }
  }
}
</script>

<style>
  #cursor {
    pointer-events: none;
    opacity: 0;
    width: 100px;
    height: 100px;
    left: 0;
    top: 0;
    position: fixed;
    background-color:white;
    z-index: 200;
    mix-blend-mode: difference;
    background-image: url('/static.gif');
    background-size: 120%;
  }

</style>