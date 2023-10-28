<template>
  <div>
    <Formulario @input="datosMostrados = $event" />
    <DatosMostrados :datos="datosMostrados" />
  </div>
</template>

<script>
import Formulario from './components/Formulario.vue';
import DatosMostrados from './components/DatosMostrados.vue';
import { ref, watch } from'vue';
export default {
  components: {
    Formulario,
    DatosMostrados
  },
  data() {
    return {
      datosMostrados: {
        paterno: '',
        materno: '',
        nombres: '',
        sexo: '',
        materia: [],
        comentarios: ''
      }
    };
  }
};
</script>
