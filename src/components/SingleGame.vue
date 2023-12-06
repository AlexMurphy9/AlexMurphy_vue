<template>
    <div :class="game.id % 2 == 1 ? 'black': 'gray'">
      <div class="flexing">
        <span id="left">
          <h1 id="title">{{game.title}}</h1>
        </span>
        <span id="right">
          <h2>Price: <span id="price">{{game.price == 0 ? "FREE" : "$" + game.price.toString()}}</span></h2>
          <h2>Rating: {{ game.rating }}/10</h2>
          <h2>Platform(s): {{game.platforms}}</h2>
          <h2>Current players: {{game.currentPlayers.toLocaleString()}}</h2>
        </span>
      </div>
      <!-- Do NOT convert these back to json to use a v-for -->
      Top user reviews:
      <div id="reviews">
        <SingleReview :review=game.reviews[0] />
        <SingleReview :review=game.reviews[1] />
        <SingleReview :review=game.reviews[2] />
      </div>

    </div> 
</template>

<script>
import SingleReview from "./SingleReview.vue"

export default {
    name: "SingleGame",
    components:{
      SingleReview
    },
    props:{
        game: Object
    },
    setup(props) {
      console.log(props.game.title); // TODO: Does not work
    }
}
</script>

<style scoped>
h2 {
    font-size: 1em;
    margin: 0;
    padding: 0;
}

h4 {
  margin: 2px
}

.gray, .black{
  color: white;
  padding: 3em;
  text-align: center;
  margin: 1em;
  border-radius: 10px;
  box-shadow: 3px 3px 3px 3px black;
}

SingleReview {
  padding: 1em;
}
.flexing {
  display: flex;
  margin-bottom: 2em;
}

@media screen and (max-width: 700px) {
  .flexing {
    display: block;
  }

  .gray, .black {
    padding-left: 0em;
    padding-right: 0em;
  }
}

#left, #right {
  flex: 50%;
}

#left {
  background: linear-gradient(rgb(50,50,50), rgb(5,5,5), rgb(50,50,50));
  border-radius: 10px;
}
#title, .black, .gray {
  font-family: Georgia, 'Times New Roman', Times, serif;
}

#price {
  color: greenyellow;
  display: inline;
}
.gray{
  background-color: rgb(77, 77, 77) !important;
}
.black{
  background-color: #000000;
}

#reviews {
  margin-top: 1em;
  font-style: italic;
}
</style>

