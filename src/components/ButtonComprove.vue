<template>
    <div class="row mt-3 justify-content-center">
        <div class="col text-center">
            <button type="submit" class="btn btn-primary mb-2" @click="comprobar">Comprobar</button>
        </div>
    </div>
</template>

<script>
import { EventBus } from '../main.js'

export default {
    methods:{
        comprobar(){
            EventBus.$emit('comprobarRespuesta')
        }
    }
}
</script>

<style>

</style>