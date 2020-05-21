<template>
  <div class="hello">
    <label><input type="checkbox" @change="toggle('april')" value="april">4月</label>
    <label><input type="checkbox" @change="toggle('july')" value="july">5月</label>
    <label><input type="checkbox" @change="toggle('june')" value="june">6月</label>
  </div>
</template>

<script>
export default {
  model: {
    prop: 'foo',
  },

  props: {
    foo: Array
  },

  mounted () {
    console.log(this.foo)
  },

  methods: {
    toggle(value) {
      let newIds = this.foo
      // id が既にあるなら削除、無いなら追加
      if (this.foo.includes(value)) {
        newIds = newIds.filter(_id => _id != value)
      } else {
        newIds.push(value)
      }

      let uniqNewIds = Array.from(new Set(newIds))

      console.log(uniqNewIds)

      this.$emit('input', uniqNewIds)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
