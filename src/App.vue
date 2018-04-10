<template>
  <div id="battlefield-container">
      <ListWarriors />
      <div class="container">
        <Battlefield />
        <ScoreBar />
      </div>
  </div>
</template>

<script>
import ListWarriors from "./components/list/list-warriors"
import Battlefield from "./components/battlefield/battlefield-table"
import ScoreBar from "./components/scorebar/scorebar"
import "./scss/app.scss"

export default {
  name: 'app',
  components:{
    ListWarriors,
    Battlefield,
    ScoreBar
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>
