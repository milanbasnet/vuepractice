<template>
 <div>Hello {{name}}</div>
 <div v-html="best"></div>
 <div v-bind:id="headingId">Heading</div>
 <button v-bind:disabled="isDisabled">Bind</button>
 <h2 class='underline'>Underlined text</h2>
 <h2 v-bind:class='status'>Status</h2>
 <h2 v-bind:class="isPromoted && 'promoted'">Promoted movie</h2>
 <h2 v-bind:class="isSoldout  ? 'sold-out':'new'" >Soldout New</h2>
 <h2 v-bind:class="['new', 'promoted']"> Newly promoted movie</h2>
 <h2 v-bind:class="[isPromoted && 'promoted', isSlldout ? 'sold-out': 'new']"> Array conditonal </h2>
 <h2 :class="{  //without v-bind it works
   promoted: isPromoted,
   new: !isSlldout,
  'sold-out':isSlldout
 }">Object conditional movie</h2>
 <h2 v-bind:style="{
   color: highlightColor,
   'font-size': headerSize + 'px',
   padding: '20px' //static value not added by below data
 }">Inline style</h2>
<!-- //better is below using object porperty -->
 <h2 v-bind:style="headerStyleObject">inline style binding with object property</h2> 
 <div v-bind:style="[baseStyleObject, successStyleObject]">Success style</div>
 <div :style="[baseStyleObject, dangerStyleObject]">Danger style</div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      name:"Milan",
      best:'<b> Messi </b>',
      headingId: 'heading',
      isDisabled: true,
      status:'danger',
      isPromoted: true,
      isSoldout:false,
      highlightColor: 'orange',
      headerSize: 40,
      headerStyleObject: {
        color: 'orange',
        fontSize: '50px',
        padding:'20px'
      },

      baseStyleObject:{
        fontSize: '50px',
        padding:'20px'
      },
      successStyleObject:{
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green'
      },
      dangerStyleObject:{
        color: 'red',
        backgroundColor: 'black',
        border: '1px solid red'
      }
    };
  },
 
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.underline{
  text-decoration: underline;
}
.promoted{
  font-style: italic;
}
.new{
  color: green;
}
.sold-out{
  color: red;
}
</style>
