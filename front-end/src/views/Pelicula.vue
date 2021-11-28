<template>
    <b-container class="bv-example-row">
    <b-row>
        <b-col>Year</b-col>
        <b-col><b-input type="text" value="2000"/></b-col>
        <b-col>Director</b-col>
        <b-col><b-input type="text" value="Steven Spielberg"/></b-col>
        
    </b-row>
    <b-row class="m-2">
        <b-col>Country</b-col>
        <b-col><b-input type="text" value="Francia"/></b-col>
        <b-col>Language</b-col>
        <b-col><b-input type="text" value="English"/></b-col>
    </b-row>

    <b-row class="m-2">
        <b-col>URL</b-col>
        <b-col>"http://perlicula/"{{id}}</b-col>
    </b-row>
    </b-container>
</template>

<script>
export default {
    data(){
        return{
            id:''
        }
    },
    created(){
        this.getId();
    },
    methods:{
        getId(){
        this.id = this.$route.params.id;
    }
    }
    
}
</script>

<style scoped>

</style>