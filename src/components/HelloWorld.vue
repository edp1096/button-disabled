<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button :disabled="!checkEnable">Extrusion lol</button>
    <br />
    <br />
    temperature / temperature min : {{temper}} / {{temperMin}}
    <br />
    <label :for="set-temper">Input temper: </label>
    <input :id="set-temper" v-model="temper" />
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  computed: {
    checkEnable() {
      let result = false
      if (this.temper > this.temperMin) {
        result = true
      }
      return result
    }
  },
  data: function() {
    return {
      temperMin: 170,
      temper: 0
    }
  }
}
</script>

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
