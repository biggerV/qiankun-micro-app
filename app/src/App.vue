<template>
  <div id="app">
    <div class="mainapp">
      <!-- 标题栏 -->
      <header class="mainapp-header">
        <h1>QianKun</h1>
      </header>
      <div class="mainapp-main">
        <!-- 侧边栏 -->
        <ul class="mainapp-sidemenu">
          <li @click="push('/')">home</li>
          <li @click="push('/about')">about</li>
          <li @click="push('/app1/')">app1</li>
          <li @click="push('/app2/')">app2</li>
        </ul>

        <main>
          <router-view />
          <div id="subapp-viewport"></div>
        </main>
      </div>
    </div>
  </div>
</template>

<script>
import "./index.js";
import "./index.less";
export default {
  methods: {
    push(subapp) {
      history.pushState(null, subapp, subapp);
    }
  }
};
</script>

<style lang="less">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
