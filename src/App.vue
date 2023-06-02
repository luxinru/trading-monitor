<template>
  <div id="app">
    <router-view />
  </div>
</template>

<style lang="scss">
@font-face {
  font-family: 'YouSheBiaoTiHei';
  src: url('~@/assets/fonts/YouSheBiaoTiHei-2.woff2') format('woff2');
}

* {
  box-sizing: border-box;
  flex-shrink: 0;

  &::-webkit-scrollbar {
    width: 4px;
    height: 4px;
  }

  &::-webkit-scrollbar-track {
    background-color: rgba(5, 143, 250, 0.2);
  }

  &::-webkit-scrollbar-thumb {
    background-color: rgba(5, 143, 250, 0.5);
  }
}

html,
body {
  margin: 0;
  padding: 0;
}

#app {
  width: 1920px;
  height: 1080px;
}
</style>
