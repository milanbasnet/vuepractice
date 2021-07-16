<template>
    <div>Milan Basnet don</div>
    <h2>{{khaja}}</h2>
    <h2 v-for="(name, index) in names" :key="name">{{index}}{{name}}</h2>
    <h2 v-for="name in fullNames" :key="name">{{name.first}} {{name.last}}</h2>

    <div v-for="actor in actors" :key="actor.name">
        <h2>{{actor.name}}</h2>
        <h3 v-for="movie in actor.movies" :key="movie">{{movie}}</h3>
    </div>

    <h2 v-for="value in myInfo" :key="value">{{value}}</h2>
    <h2 v-for="(value, key, index) in myInfo" :key="value">{{index}}  {{key}}  {{value}}</h2>

    <template v-for="name in names" :key="name">
        <h2>{{name}}</h2>
        <hr/>
    </template>


    <!-- conditional list rendering -->

    <template v-for="name in names" :key="name">
        <h2 v-if="name==='suraj'">{{name}}</h2>
    </template>

</template>

<script>
export default {
    name:'list',
    data() {
        return{
            khaja:'dahi chiura',
            names: ['Milan', 'suraj', 'gasi'],
            fullNames:[
                {first: 'Milan', last:'Basnet'},
                {first: 'anisha', last:'Basnet'},
                {first: 'sarbagya', last:'Basnet'}
            ],
            actors:[
                {
                    name: 'Christian Bale',
                    movies: ['Prestige', 'batman']
                },
                {
                    name: 'di caprio',
                    movies: ['Dgango unchained', 'titanic']
                }
                
            ],

            myInfo:{
                name: 'Cilian Murphy',
                movie: 'dunkirk',
                role: 'short'
            }
        };
        
    },
}
</script>

<style>
#listren{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>