
<template>
    <div>
        <h1 class="text-center">Gestionar Datos AWS</h1>
        <hr>
        <table class="table" >
            <thead class="thead-dark">
            <tr>
                <th scope="col">id</th>
                <th scope="col">paramuno</th>
                <th scope="col">paramdos</th>
                <th scope="col">arn</th>
                <th scope="col">resultado</th>
                <th scope="col">date_of_creation</th>
                <th scope="col">date_of_last delete</th>
                <th scope="col">delete_at</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="registros in dataDos" :key="registros.id" >
                <th scope="row">{{registros.id}}</th>
                <td>{{registros}}</td>
                <td>{{registros.paramuno}}</td>
                <td>{{registros.paramdos}}</td>
                <td>{{registros.arn}}</td>
                <td>{{registros.resultado}}</td>
                <td>{{registros.date_of_creation}}</td>
                <td>{{registros.date_of_last_delete}}</td>
                <td>{{registros.delete_at}}</td>
            </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    data() {
        return {
            dataDos: [],
        }
    },
    created(){
        this.list();
    },
    beforeMount() {
        this.list();
    },
    methods: {
        async list() {
            try{
                const {
                    data
                } = await axios.get('hola');
                    this.dataDos = data;
            }catch(ex){
                console.log(ex);
            }


        }

    }

}
</script>
<style>

</style>
