<template>
  <div v-bind="dval">Ahoj</div>
  <p>
    {{ ok ? 'YES' : 'NO' }}
  </p>
  <button @click="toggleButton">Toggle</button>
  <p>
    {{ Math.PI }}
  </p>
  <div>
    <input type="range" min="0" max="50" v-model="rangeVal">
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
      rangeVal: 0,
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