<template>
  <div v-bind="dval">Ahoj</div>
  <p>
    {{ ok ? 'YES' : 'NO' }}
  </p>
  <button @click="toggleButton">Toggle</button>
  <p v-if="ok">
    {{ Math.PI.toPrecision(rangeVal) }}
  </p>
  <ul>
    <li v-for="i in [1,2,3]">{{rangeVal}}</li>
  </ul>
  <div>
    <input type="range"  min="1" max="30" v-model="rangeVal">
    {{ rangeVal }}
  </div>
</template>

<script>

export default {
  name: "MyComp",
  data() {
    return {
      tval: 'dalsi text',
      dval: {
        name: 'nejaky-div',
        id: 'id-div'
      },
      ok: true,
      rangeVal: 1,
    }
  },
  methods: {
    toggleButton() {
      this.ok = !this.ok
   },
    getDate() {
      return new Date()
    }
  }
}

</script>

<style scoped>

</style>