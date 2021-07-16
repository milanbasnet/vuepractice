<template>
 <div :style="nameObject">Hello {{name}}</div>
 <!-- conditonal rendering -->
 <h2 v-if="num===0">Number is zero</h2>
 <h2 v-else-if="num<0">Number is negative</h2>
 <h2 v-else-if="num>0">Number is positive</h2>
 <h2 v-else>Not a number</h2>

 <template v-if="display">  <!-- if there is div it would not work-->
     <h2>Milan</h2>
     <h2>Milan</h2>
     <h2>Milan</h2>
 </template>

 <h2 v-show="showElemnet">v-show</h2> <!-- when conditon is false it remains in the dom with display-none but 
 if we use v-if and if the condition is false it wont be shown in the dom -->
</template>

<script>

export default {
  name: 'Ren',
  data(){
    return {
        name: 'Milan',
        nameObject:{
            color:'black',
            backgroundColor:'green',
            'font-size': 30 +'px',
            'text-style': 'underline'
        },
        num: 'haha',
        display: true,
        showElemnet: true
      };
  },
}
</script>

<style>
#ren{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
