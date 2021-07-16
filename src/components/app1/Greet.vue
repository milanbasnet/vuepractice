<template>
    <h2>Hello {{name}} he is {{heroName}} </h2>
</template>

<script>
export default {
    name:'Greet',
    props:['name', 'heroName'],
    data() {
        return{
        }
        
    },
}
</script>

<style>
#greet{
       font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>