<template>
  <div id="app">
  <h1>{{title}}</h1>
  <input type="text" v-model="newItem" @keyup.enter="addNew">
  <ul>
  <li v-for=" item in items" v-bind:class="{finshed: item.isfinshed}" @click="toggleFinsh(item)">
      {{item.label}}
  </li>
</ul>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      title: 'Hello world!',
      items: [
        {
          label: 'coding',
          isfinshed: false
        },
        {
          label: 'walking',
          isfinshed: true
        }
      ],
      newItem: ''
    }
  },
  methods: {
    toggleFinsh: function (item) {
      item.isfinshed = !item.isfinshed
    },
    addNew: function () {
      console.log(this.newItem)
      this.newItem = ''
    }
  },
  wahrch: {
    items: {
      handler: function (val, oldVal) {
        console.log(val, oldVal)
      },
      deep: true
    }
  }
}
</script>

<style>
.finshed{
  text-decoration: underline;
}
html {
  height: 100%;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

#app {
  color: #2c3e50;
  margin-top: -100px;
  max-width: 600px;
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
}

#app a {
  color: #42b983;
  text-decoration: none;
}

.logo {
  width: 100px;
  height: 100px
}
</style>
