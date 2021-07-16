<template>
   <div>
       <!-- <slot></slot> -->
       <slot name="header"></slot>
       <slot ></slot>
       <slot name="footer"></slot>
      
   </div>
</template>

<script>
    export default {
        name:'Slot',
        data(){
            return{

            };
        },
    }
</script>

<style scoped>

</style>