<template>
    <h2>{{name}}</h2>
    <div>
        <button v-on:click="name = 'Milan',increment(1)">Change Name</button>  <!-- another method is attached by separated by comma -->
    </div>
    <h2>{{count}}</h2>
    <!-- without method -->
    <!-- <div>
        <button v-on:click="count=count+1">Increment</button>
        <button v-on:click="count=count-1">decrement</button>
    </div> -->
    <div>
        <button v-on:click="increment(1)">Increment</button>
        <button v-on:click="increment(2)">Increment by 2</button>
        <button @click="decrement(3)">decrement by 3</button>
        <button @click="decrement(1, $event)">decrement</button>
    </div>
</template>

<script>
export default {
    name:'Event',
    data() {
        return{
            name:'Anisha',
            count: 0
        };
    },
    methods: {
        increment(num){
            // this.count +=1
            this.count= this.count+num  //this.count= count+1 is not working 
        },
        decrement(num, event){
            this.count -=num
            console.log('Event', event)
        }
    },
}
</script>

<style>
#event{
    font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
 </style>

