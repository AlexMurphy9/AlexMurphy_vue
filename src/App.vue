<template>
  <!-- Step 3: use the component -->
  <MyHeader authorName="Alex Murphy" />
  <GameBox :games=games />
  <!-- <MyFooter /> -->
  <p id="disclaimer"><em>Disclaimer: information was fetched on November 26, 2023 at 7:40 PM.</em></p>
</template>

<script>
// Step 1 : you import the component
import MyHeader from './components/MyHeader.vue'
import GameBox from './components/GameBox.vue'
// import MyFooter from './components/MyFooter.vue'

export default{
  name: 'App',
  // Step 2: Register the component
  components:{
    MyHeader,
    GameBox
    // MyFooter
  },
  data(){
    return {
      games: []
    }
  },

  methods:{     
    async fetchgames(){
      // const res = await fetch("http://localhost:5356/api")
      const res = await fetch("https://alexmurphynodeserver-b521978c0ea2.herokuapp.com/api")
      const data = await res.json();
      const dataReal = data[0]["games"]; // TODO: Edit this or the DB
      console.log(dataReal);
      return dataReal;
    }

  },
  async created(){
    this.games = await this.fetchgames();
    console.log(this.games);
  }
}
</script>

<style >
    #disclaimer{
        text-align: center;
    }

    html {
      background-color: rgb(1, 6, 49);
      color: rgb(255, 255, 255);
      font-size: 1.7em;
    }
</style>