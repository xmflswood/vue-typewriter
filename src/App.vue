<template>
  <div id="app">
    <button @click="type">start.</button>
    <typewriter class="tl" ref="typewriter" :interval="50" :style="{visibility: status}">
      <div class="comments">
        <p>/**</p>
        <p><span class="space"></span>*imitate typing</p>
        <p><span class="space"></span>*blabla bla...</p>
        <p><span class="space"></span>*bla...</p>
        <p>*/</p>
      </div>
    </typewriter>
  </div>
</template>

<script>
import typewriter from './components/vue-typewriter.vue'

export default {
  name: 'app',
  components: { typewriter },
  data () {
    return {
      status: 'hidden'
    }
  },
  methods: {
    type () {
      this.status = 'visible'
      this.$refs.typewriter.$emit('typewrite')
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.tl {
  text-align: left;
}
.comments {
  color: #3f7f5f;
}
.space {
  display: inline-block;
  padding-left: 7px;
}
</style>
