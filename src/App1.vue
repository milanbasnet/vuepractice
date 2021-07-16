<template>
    <div>
        <!-- <Watcher /> -->
        <!-- <Greet name="Milan" heroName="don"/>
        <Greet name="suraj" heroName="arko don " />
        <Greet name="gasi" heroName=" thulo don" />
        <Greet :name="name" :heroName="sport" /> -->
         <!-- to pass dynamic values to props we can bind data properties so we create data properties -->
       
        <Article class="haha" title="Article title"  :likes="50" :isPublished="true" />  <!-- without v-bind likes is passing as string -->
    </div>
    <h3>nested username - {{username}}</h3>
    <!-- <Slot /> -->
     <!-- in slot we use as below -->  
     <!-- <Slot>Slot content</Slot>
     <Slot><h2>Slot content in thulo</h2></Slot> -->

     <!-- here is multiple slot sections to pass slot from parent -->
     <Slot>
         <template v-slot:header>
             <h2>Header</h2>
         </template>
         <template v-slot:default>
             <h2>This is content slot</h2>
         </template>
         <template v-slot:footer>
             <h2>footer</h2>
         </template>
    </Slot>
    <Slotprops>
        <template v-slot:namelist= "slotProps">
            {{slotProps.firstName}} {{slotProps.lastName}}
             </template>
     </Slotprops>
    <Slotprops>
        <template v-slot:namelist= "slotProps">
            {{slotProps.lastName}} {{slotProps.firstName}}
             </template>
     </Slotprops>
    <Slotprops>
        <template v-slot:namelist= "slotProps">
            {{slotProps.firstName}}
             </template>
     </Slotprops>

     <div>
         <button @click="activeTab ='TabA'">Tab A</button>
         <button @click="activeTab ='TabB'">Tab B</button>
         <button @click="activeTab ='TabC'">Tab C</button>

        <!-- component tag below renders all tabs and works as below 3 tabs -->
         <!-- prevent re rendering of component and form value not dissapeared -->
        <keep-alive>
        <component :is="activeTab" /> 
        </keep-alive>
         <!-- <TabA v-if="activeTab ==='TabA'" />
         <TabB v-if="activeTab ==='TabB'"/>
         <TabC v-if="activeTab ==='TabC'"/> -->
     </div>
      
</template>

<script>
// import Watcher from './components/Watcher.vue';
// import Greet from './components/app1/Greet.vue';
import Article from './components/app1/Article.vue';
import Slot from './components/app1/Slot.vue';
import Slotprops from './components/app1/Slotprops.vue';

import TabA from './components/app1/TabA.vue';
import TabB from './components/app1/TabB.vue';
import TabC from './components/app1/TabC.vue';

export default {
    name: 'App1',
  components: { 
    // Watcher,
    // Greet,
    Article,
    Slot,
    Slotprops,
    TabA,
    TabB,
    TabC
    },
   data(){   //data properties where data is function
       return{
           name:'Milan', //which returns objects 
           sport: 'football',
           activeTab: 'TabA'
       }
   },
//    provide:{    // this throws error so we make function as provide and return value
//        username:this.name
//    }
   provide(){   
       return {
         username: this.name,
       }
   }
}
</script>

<style>
#app1{
       font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>