<template>
    <div>
        <h2>nested to article</h2> 
        <h3>nested username- {{username}}</h3>
    </div>
</template>

<script>
    export default {
        name:'Nested',  //this was imported to Article.vue and article was to app1 but shown error
        inject:['username']
        
    }
</script>

<style scoped>

</style>