<template>
  <div id="app">
    <navbar/>
    <img alt="Vue logo" src="./assets/logo.png">
  </div>
</template>

<script>
import axios from 'axios';
import Navbar from './components/Navbar.vue';

export default {
  name: 'App',
  components: {
    Navbar,
  },

  data() {
    return {
      teams: [],
      games: [],  
    }
  },

  mounted() {
    axios.get("https://api.collegefootballdata.com/teams/fbs").then (res => {
      let teamResponse = res.data;
      let bigTen = teamResponse.filter(team => team.conference === "Big Ten");
      this.teams = bigTen;
      console.log(this.teams);
    });

    axios.get("https://api.collegefootballdata.com/games?year=2020&seasonType=regular&conference=B1G").then (res => {
        let gameResponse = res.data;
        this.games = gameResponse;
        console.log(this.games);
    });
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
