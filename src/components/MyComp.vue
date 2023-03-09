<template>
  <input type="text" v-model="inputVal1">
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
  <p>
    {{ suffixText }}
  </p>
</template>

<script>

export default {
  name: "MyComp",
  data() {
    return {
      inputVal1: '',
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
  },
  computed: {
    suffixText() {
      return this.inputVal1 + ' some suffix'
    }
  }
}

</script>

<style scoped>

</style>