<template>
  <div>
    "{{ review }}"
  </div>
</template>

<script>
export default {
    name: "SingleReview",
    props:{
        review: String
    },
    setup(props) {
      console.log(props.review); // TODO: Does not work
    }
}
</script>

<style scoped>
  div {
    padding-top: 0.5em;
    padding-bottom: 0.5em;
    padding-left: 10%;
    padding-right: 10%;
    background: linear-gradient(rgb(50,50,50), rgb(5,5,5), rgb(50,50,50));
    border-radius: 10px;
    margin: 7px;
  }
</style>
