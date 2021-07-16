<template>
    <div>
        <h3 v-for="name in names" :key="name.firstName">
            <!-- we pass data from slot to the parent component  -->
            <slot name="namelist" :firstName="name.firstName"  :lastName="name.lastName"> </slot>
        </h3>
    </div>
</template>

<script>
    export default {
        name:'Slotprops',
        data(){
            return{
                names:[
                    {
                        firstName: 'Milan',
                        lastName: 'Basnet'
                    },
                    {
                        firstName: 'Suraj',
                        lastName: 'Neupane'
                    },
                    {
                        firstName: 'Suman',
                        lastName: 'Ghimire'
                    },
                ]
            }
        }
    }
</script>

<style scoped>

</style>