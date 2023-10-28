<template>
    <div class="formulario-container">
        <h2>Formulario de Datos</h2>
        <div class="form-group">
            <label for="paterno">Apellido Paterno:</label>
            <input v-model="paterno" type="text" id="paterno" />
        </div>
        <div class="form-group">
            <label for="materno">Apellido Materno:</label>
            <input v-model="materno" type="text" id="materno" />
        </div>
        <div class="form-group">
            <label for="nombres">Nombres:</label>
            <input v-model="nombres" type="text" id="nombres" />
        </div>
        <div class="form-group">
            <label>Sexo:</label>
            <input type="radio" id="hombre" value="Hombre" v-model="sexo" />
            <label for="hombre">Hombre</label>
            <input type="radio" id="mujer" value="Mujer" v-model="sexo" />
            <label for="mujer">Mujer</label>
        </div>
        <div class="form-group">
            <label for="materia">Materia:</label>
            <select name="materia" id="materia">
                <option value="Calculo">Calculo</option>
                <option value="Fisica">Fisica</option>
                <option value="Estadistica">Estadistica</option>
                <option value="INF-121">INF-121</option>
            </select>
        </div>
        <div class="comentarios-container">
            <label for="comentarios">Comentarios:</label>
            <textarea v-model="comentarios" id="comentarios"></textarea>
        </div>
    </div>
</template>


<script>
import { ref, watch } from 'vue';

export default {
    data() {
        return {
            paterno: '',
            materno: '',
            nombres: '',
            sexo: '',
            materia: [],
            comentarios: ''
        };
    },
    setup() {
        const formData = ref({
            paterno: '',
            materno: '',
            nombres: '',
            sexo: '',
            materia: [],
            comentarios: ''
        });

        const submitForm = () => {
            const data = {
                paterno: formData.value.paterno,
                materno: formData.value.materno,
                nombres: formData.value.nombres,
                sexo: formData.value.sexo,
                materia: [...formData.value.materia],
                comentarios: formData.value.comentarios
            };
            formData.value = data;
        };

        
        watch(formData, () => {
            this.$emit('input', formData.value);
        });

        return {
            formData,
            submitForm
        };
    }
};
</script>
<style scoped>
.formulario-container {
    text-align: left; 
    margin-left: auto; 
    margin-right: auto; 
}

</style>

