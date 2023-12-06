<template>
    <div v-for="game of games" :key="game.id">
        <SingleGame :game=game />
    </div>
</template>

<script>
import SingleGame from "./SingleGame.vue"

export default {
    name: "GameBox",
    props:{
        games: Array,
    },
    async created() {
        console.log(this.games);
    },
    components:{
        SingleGame
    }
}
</script>

<style scoped>
    li {
        color: #000000;
        background-color: #707070;
    }
</style>