<template>
  <h1>{{ job.title }}</h1>
  <p>The job id is {{ $route.params.id }} </p>
  <p>The job id is {{ id }} </p>
  <p>{{ job.details }}</p>
</template>

<script>
export default {
   props:['id'],
   mounted(){
    fetch('http://localhost:3000/jobs/' + this.id)
    .then((res) => res.json())
    .then(data => this.job = data)
    .catch(err => console.log(err.message))
},
    data(){
  return{
      id: this.$route.params.id,
      job:null

}
}

}
</script>

<style>

</style>