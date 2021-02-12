<template>
    <div>
        <h1 class="text-center">Formulario Aws</h1>
        <hr>
            <div class="form-group" >
                <label class="form-label">Param uno</label>
                <input v-model="datatres.paramUno"  type="number" class="form-control"   >
            </div>
            <div class="form-group">
                <label for="" class="form-label">Param dos</label>
                <input v-model="datatres.paramDos"  type="number" class="form-control" >
            </div>

            <div class="form-group">
                <label  lass="form-label">Arn</label>
                <input v-model="datatres.arnUno"  type="text" class="form-control" >
            </div>

        <div class="form-group">
            <label  lass="form-label">Nombre</label>
            <input v-model="datatres.nombreUno"  type="text" class="form-control" >
        </div>
        <div class="mb-3 form-check">
            <input type="checkbox" class="form-check-input" id="exampleCheck1" required>
            <label class="form-check-label" for="exampleCheck1">Check me out</label>
        </div>
            <div class="mb-3">
                <button type="submit" class="btn btn-primary" @click="registrar" >Submit</button>
            </div>

    </div>
</template>
<script>
export default {
    data() {
        return{
               datatres:{
                   paramUno: "",
                   paramDos: "",
                   arnUno: "",
                   nombreUno: ""

               }

        }
            },

    methods: {
        registrar: async function() {
            await axios.post('/peticionaxios',{
                datatres: this.datatres,

            }).then(response =>{
                if(response.status==201){
                    this.datatres.paramUno == "";
                }
            }).catch(e =>{
                console.log(e);
            });
            }

        }


}
</script>
<style>

</style>
