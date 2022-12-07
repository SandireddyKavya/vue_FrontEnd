<template>
<div class="container">
  <!-- Step 3 you must use the imported component-->
  <HeaderTop bookName= " Flight Management" authorName="Details of Flights"/>
  <flightBox :flights="flights"/>  
  <button class="button" onclick="window.open('https://busy-cyan-lemur-tutu.cyclic.app','_blank')">Pilot Info</button>

</div>
  </template>
  <script>
  // Step 1:  import HeaderTop.vue
 
  import HeaderTop from './components/HeaderTop.vue'
  import flightBox from './components/flightBox.vue'
   // Step 2: Register the imported component
  export default                                
  {                                               
    name: 'App',
    components: {
      HeaderTop,
      flightBox
    } ,
    data(){
      return {
        flights: []
      }
    },
    methods:{

      async fetchBooks()
      {
        const res = await fetch("https://busy-cyan-lemur-tutu.cyclic.app/api")
        const data= await res.json()
        console.log(data.flights)
        return data.flights
      }
      
    },

    async created(){
         this.flights = await this.fetchBooks()

      }
  }
  
   
    </script>
    <style >
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
    *{
      box-sizing: border-box;margin: 0;padding: 0;
      }
      body
      {
        font-family: "Montserrat", sans-serif;
    }
      .container{
        max-width: 1000px;
        margin: 30px auto;
        overflow: auto;
        min-height: 300px;
        border: 0.3em solid black;
        padding: 30px;
        border-radius: 5px;
        }
        body {
 background-image: url("flight.jpg") ;
 background-repeat: no-repeat, repeat;
 background-size: cover;
  

}
.button {
    width: 100%;
    height: 50px;
    margin-top: 10px;
    color:white;
    background-color:blueviolet;
}
      </style>