<template>
    <div>
        <h2>Article component</h2>
        <h2 v-bind="$attrs">{{title}}</h2>
        <h2>Likes- {{likes}}</h2>
        <h2>Published- {{isPublished ? 'yes' :'no'}}</h2>
    </div>
    
        <!-- <Nested /> -->
</template>

<script>
// import Nested from './components/app1/Nested.vue'
    export default {
        name:'Article',
        // components:{
        //     Nested,
        // },
        props:{
            title: String,
            likes: Number,
            isPublished: Boolean
        }
    }
</script>

<style scoped>

</style>