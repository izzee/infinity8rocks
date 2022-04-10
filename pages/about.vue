<template>
  <div class="page-content">
    <ul class="acrostic">
      <li><b>E</b> xtrovert</li>
      <li><b>L</b> ovely</li>
      <li><b>L</b> adylike</li>
      <li><b>I</b> maginative</li>
      <li><b>E</b> vil</li>
      <li><b>S</b> ecretive</li>
      <li><b>A</b> wesome</li>
      <li><b>M</b> usic⸻loving</li>
      <li><b>I</b> ntrovert</li>
      <li><b>S</b> illy</li>
    </ul>
  </div>
</template>

<style scoped lang="scss">
  .page-content {
    flex: 1;
    display: flex;
    @include s(gap);
    @include rounded;
    align-items: center;
    justify-content: space-between;
    box-shadow: 0 0 32px 16px $black inset;
    background-image: url('static/images/optimized-dna-1.gif');
    background-repeat: no-repeat;
    background-size: 100% 100%;
    box-sizing: border-box;
    filter: blur(.5px);
  }

  .acrostic {
    color: $blue;
    background-color: #000000aa;
    list-style: none;
    opacity: .9;
    flex: 1;
    height: 100%;
    display: flex;
    margin: auto;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    text-align: left;
    box-sizing: border-box;
    @include s(padding);

    li {
      color: $skyblue;
      margin: 4px;
      padding: 0px 8px;
      background-color: $blue;
      border-radius: 32px;
      font-size: 16px;
      line-height: 1.5;
      box-shadow: 0 -2px 8px $black inset, 0 0 16px 8px $black;
      b {
        color: $green;
      }
      @include bp(xs) {
        margin: 8px;
        padding: 0px 16px;
        font-size: 24px;
        line-height: 1.33333333;
        box-shadow: 0 -4px 16px $black inset, 0 0 24px 8px $black;
      }
      @include bp(md) {
        font-size: 32px;
        line-height: 1.25;
      }

    }

  }
</style>