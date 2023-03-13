<template>
  <input type="text" v-model="inputVal1">
  <div v-bind="dval">Ahoj</div>
  <p>
    {{ ok ? 'YES' : 'NO' }}
  </p>
  <button @click="toggleButton" :style="btnClass">Toggle</button>

  <ul>
    <li v-for="({message}, index) in someList">{{ index }} - {{ message }}</li>
  </ul>
  <div>
    <input type="range" min="1" max="30" v-model="rangeVal">
    {{ rangeVal }}
  </div>
  <p :class="{'para': ok}">
    {{ suffixText }}
  </p>
  <p v-if="ok">
    {{ Math.PI.toPrecision(rangeVal) }}
  </p>
  <p v-else>Not ok</p>
  <template v-if="ok">
    <h2>Blabla</h2>
  </template>
  <h2 v-show="ok">Neco</h2>
  <ul>
    <li v-for="(value, key, index) in myObject">
      {{ index }}. {{ key }}: {{ value }}
    </li>
  </ul>

  <span v-for="i in 10">{{ i }}</span>

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
      someList: [{message: 'Foo'}, {message: 'Bar'}],
      myObject: {
        title: 'How to do lists in Vue',
        author: 'Jane Doe',
        publishedAt: '2016-04-10'
      }

    }
  }
  ,
  methods: {
    toggleButton() {
      this.ok = !this.ok
    }
    ,
    getDate() {
      return new Date()
    }
  }
  ,
  computed: {
    suffixText() {
      return this.inputVal1 + ' some suffix'
    }
    ,
    btnClass() {
      return {
        'font-size': 12 + (+this.rangeVal) + 'px'
      }
    }
  }
}

</script>

<style scoped>
.para {
  background-color: aquamarine;
}
</style>