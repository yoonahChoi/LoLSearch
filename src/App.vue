<template>
  <div id="app">
    <input-box v-bind:value="summoner"></input-box>
    <div>{{rotations}}</div>
  </div>
</template>

<script>
import axios from 'axios'
import {apiKey} from '../config/api_key'
import InputBox from './components/InputBox'

export default {
  name: 'App',
  data () {
    return {
      summoner: '',
      rotations: ''
    }
  },
  created () {
    this.fetchRotation()
  },
  components: {
    'input-box': InputBox
  },
  methods: {
    fetchRotation () {
      axios.get(`https://kr.api.riotgames.com/lol/platform/v3/champion-rotations?api_key=${apiKey}`)
        .then(res => {
          this.rotations = res.data.freeChampionIds
        })
    }
  }
}
</script>

<style>

</style>
