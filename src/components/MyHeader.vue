<template>
    <div>
        <h2 id="animate">Video Game Hub</h2>
        <p>Find out information about top grossing video games on Steam!</p>
        <h5><em>by {{authorName}}</em></h5>
    </div>
</template>

<script>
    export default{
        name: 'MyHeader',
        props:{
            authorName: String,
            gameName: String
        }
    }

</script>

<style scoped>
    div{
        text-align: center;
        color: white;
    }
</style>
