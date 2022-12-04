<template>
<div>
  <div class='container'>
    <Header/>
   </div>
  <div class="space">
    <AddEvent @add-event='eventAdd'/>
    <Event @delete-event="deleteEvent" :events="event"/>

  </div>
    
</div>

</template>
 
<script>
import Header from './components/Header.vue'
import Event from './components/Event.vue'
import AddEvent from './components/AddEvent.vue'

export default {
  name: 'App',
  components: {
  Header,
  Event,
  AddEvent

  },
  data(){
    return{
      event: []
    }
  },
  methods:{
    eventAdd(events){
  this.event=[...this.event, events]
    },
    deleteEvent(id){
      if(confirm("are you sure you want to delete this event")){
      this.event = this.event.filter((e) => e.id !== id)

      }
    }
  },
  mounted(){
    this.event= [
      {
        social: "Instagram Hangout",
        id: 1,
        date: "21st december 2022",
        color:"blue"
      },
      {
        social: "Christmas Party",
        id: 2,
        date: "25th december 2022",
        color:"red"
      },
      {
        social: "Altschool Meet up",
        id: 3,
        date: "23rd december 2022",
        color:"black"
      },
      {
        social: "White house Party",
        id: 4,
        date: "31st december 2022",
        color:"white"
      },
      {
        social: "Naija End of the year Party",
        id: 5,
        date: "27th december 2022",
        color:"green"
      }
    ]
  }
}
</script>

<style>

*{
  margin: 0;
  padding: 0;
  
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: cyan;
  margin: 0;
  padding: 0;
  background-color: #161616;
  height: 100vh;
  

}
.container{
  border: 1px solid black;
  width: 100%;
  background:white;
  color: white;
  padding: 8px;
  border: none;
  box-shadow: 0 1px 1.5px 2px rgba(0,0,0,0.1);

}
.space {
  display: flex;
  justify-content: space-around;
}
</style>
