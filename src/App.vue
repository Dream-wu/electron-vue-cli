<template>
  <div id="app">
    <div class="app-control">疫情实况</div>
    <div class="app-container">
       <H1 class="title">累计确诊</H1>
      <h1 class="num">{{total.confirm}}</h1>
    </div>
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  // components: {
  //   HelloWorld
  // }
  data() {
    return {
      today: {},
      total: {}
    }
  },
  mounted() {
    fetch('https://c.m.163.com/ug/api/wuhan/app/data/list-total?t=320926046801').then(res => res.json()).then(res => {
      const { chinaTotal } = res.data
      const { today, total} = chinaTotal
      this.today = today
      this.total = total
    })
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
}
html, body {
  height: 100%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
  margin-top: 0;
  display: flex;
  flex-direction: column;
  .app-control {
    height: 30px;
    border-bottom: 1px solid whitesmoke;
    -webkit-app-region: drag;
    display: grid;
    place-items: center;
  }
  .app-container {
    flex: 1;
    display: grid;
    place-items: center;
    .title {
      color: mediumslateblue;
      opacity: 0.5;
    }
    .num {
      color: mediumvioletred;
      font-size: 64px;
    }
  }
}
</style>
