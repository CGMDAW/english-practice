<template>
    <div class="row mt-3 justify-content-center">
        <div class="col text-center">
            <button type="submit" class="btn btn-primary mb-2" @click="comprobar">Comprobar</button>
        </div>
    </div>
</template>

<script>

export default {
    methods:{
        comprobar(){
            this.$emit('comprobarRespuesta')
        }
    }
}
</script>

<style>

</style>