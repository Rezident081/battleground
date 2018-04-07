<template>
  <div id="battlefield-container">
      <ListWarriors/>
  </div>
</template>

<script>
import ListWarriors from "./components/list/list-warriors"
import "./scss/app.scss"

export default {
  name: 'app',
  components:{
    ListWarriors
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>
