<template>
  <div id="app">
    <h1>テスト</h1>
    <ChildrenComponent
      v-model="foo"
    >
    </ChildrenComponent>
  </div>
</template>

<script>
import ChildrenComponent from './components/ChildrenComponent.vue'

export default {
  components: {
    ChildrenComponent
  },

  data () {
    return {
      foo: []
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
