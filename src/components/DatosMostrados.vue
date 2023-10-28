<template>
    <div class="Datos-container">
        <h2>Datos Ingresados</h2>
        <p>Apellido Paterno: {{ datos.paterno  }}</p>
        <p>Apellido Materno: {{ datos.materno }}</p>
        <p>Nombres: {{ datos.nombres }}</p>
        <p>Sexo: {{ datos.sexo }}</p>
        <p>Materias: {{ datos.materia }}</p>
        <p>Comentarios: {{ datos.comentarios  }}</p>
    </div>
</template>

<script>
export default {
    props: {
        datos: Object
    }
};
</script>
<style scoped>
.Datos-container {
    text-align: left; 
    margin-left: auto; 
    margin-right: auto; 
}
</style>


