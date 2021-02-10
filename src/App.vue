<template>
  <div id="app" class="container-fluid pt-5">

    <practice-component 
        v-for="(item,index) in coleccion" 
        :key="index" 
        :part1="item.part1" 
        :solution1="item.solution1" 
        :part2="item.part2" 
        :solution2="item.solution2"
        :part3="item.part3"
        :index="index + 1 "
     ></practice-component>
    
    <button-comprove></button-comprove>


  </div>
</template>

<script>
import axios from 'axios'
import PracticeComponent from './components/PracticeComponent.vue'
import ButtonComprove from './components/ButtonComprove.vue'

export default {
  name: 'App',
  data(){
    return {
      coleccion: []
    }
  },
  created(){
    this.obtenerDatos()
  },
  methods:{
    obtenerDatos: function(){

      var url = `https://english-practice-362b6-default-rtdb.firebaseio.com/Conditionals1.json`;

       axios
          .get(url)
          .then(response => {
              
            this.coleccion = response.data

            })
            .catch(error => {
              console.log(error)
            })
    }
  },

  components: {
    PracticeComponent,
    ButtonComprove
  }
}

</script>

<style>
</style>
