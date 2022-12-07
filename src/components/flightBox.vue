<template>
    
    
    <div v-for="flight in flights" :key="flight.id">
        <flightItem :flight="flight"/>
    </div>

</template>
<script>

import flightItem from './flight-Item.vue'
export default {
    name: 'flightBox',
    components:{
    flightItem
    },
    props:{
        flights: Array
    }
}
</script>
<style scoped>

.bookbox{
    background-color: bisque;
    padding:1 em;
    color: gray;
}


</style>
