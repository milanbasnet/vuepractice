<template>
    <div>hello</div>
    <h2>add mehtod- {{ add(34,56,67) }}</h2>
    <h2>Multiply mehtod - {{multiply(10)}}</h2>
    <h2>Multiply mehtod - {{multiply(baseValue)}}</h2>
</template>


<script>
export default {
    name:'Method',
    data() {
        return{
            baseMultiplier: 5,
            baseValue: 300
        };
    },
        methods:{
                add(a,b,c){
                    return a+b+c
                },

                multiply(num){
                    return num* this.baseMultiplier
                }
            },
}
</script>

<style>
#method{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>