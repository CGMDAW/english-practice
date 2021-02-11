<template>

    <div>
        <div class="row mt-2 justify-content-center">
             <p class="badge badge-success mt-2 align-self-center">{{ index }}</p>
            <div class="col-11">
                <div class="input-group">
                    <div class="input-group-prepend">
                        <label class="input-group-text" for="inputGroupSelect01">{{part1}}</label>
                    </div>
                    <input type="text" aria-label="solution 1" v-model="value1" :class="acierto1 ? '' : 'text-danger'" class="form-control text-center" >
                    <div class="input-group-append">
                        <label class="input-group-text"  for="inputGroupSelect02">{{part2}}</label>
                    </div>
                    <input type="text" aria-label="solution 2" v-model="value2" :class="acierto2 ? '' : 'text-danger'" class="form-control text-center">
                    <div class="input-group-append">
                        <label class="input-group-text" for="inputGroupSelect02">{{part3}}</label>
                    </div>
                </div>
            </div>
        </div>
        <!--<div class="row mt-3">
            <div class="col-4">
                <button-comprove @comprobarRespuesta="comprobar"></button-comprove>
            </div>
        </div>-->
        
    </div>
    
</template>

<script>
//import ButtonComprove from './ButtonComprove.vue'

export default {
    components:{
       // ButtonComprove
    },
    data(){
        return{
            acierto1: true,
            acierto2:true,
            value1: '',
            valor2: '',
        }
    },
    props:{
        corregir: false,
        part1: String,
        part2: String,
        part3: String,
        solution1: String,
        solution2: String,
        index: Number
    },
    watch: {
        corregir: function(newVal, oldVal) {
            if (newVal) {
                // corregir = true
                this.comprobar();
            }
        }
    },
    methods:{
        comprobar(){
            if(this.value1 != this.solution1){
                this.acierto1 = false;
                this.value1 = this.solution1
            }
            else{
                this.acierto1 = true;
                
            }

            if(this.value2 != this.solution2){
                this.acierto2 = false;
                this.value2 = this.solution2
            }
            else{
                this.acierto2 = true;
                
            }
        }
    }
}
</script>

<style>

</style>