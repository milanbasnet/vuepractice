<template>
  <h2>Volume Tracker (0-20)</h2>
  <h3>current volume- {{volume}}</h3>
  <div>
      <button @click="volume +=2">Increase</button>
      <button @click="volume -=2">Decrease</button>
  </div>
</template>

<script>
export default {
    name: 'Watcher',
    data() {
        return{ 
            volume:0
        };
    },
    methods:{
       
    },
    watch:{
        volume(newValue, oldValue){
            if(newValue>oldValue && newValue===16){
                alert('high volume is not preferable')
            }
        }
    }

}
</script>

<style>
#watcher{
       font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>