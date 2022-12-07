<template>
    <div :class="flight.published ? 'green': 'red'">
    <h2>{{flight.title}}</h2>
    <h4>{{flight.year}}</h4>
    <h4>{{flight.location}}</h4>
    <h4>{{flight.location1}}</h4>
    <h4>{{flight.type}}</h4>
    <h4>{{flight.Fare}}</h4>
</div>
</template>
<script>
export default{
    name:'flight-Item',
    props :{
flight: Array
    }
}


</script>
<style scoped>
h4{
    margin: 2px;
}
div{
    background-color:crimson;
    color: black;
    padding: 1em;
    margin:5px;
}
.red{
    background-color: red;
}
.green{
    color:white;
}
</style>