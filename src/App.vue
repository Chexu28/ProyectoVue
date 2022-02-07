<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <HelloWorld msg="Mitos de la NBA" autor="Jesus"/>
   <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
  <tabla-personas v-bind:personas="personas" />
  <formulario-persona @add-persona="agregarPersona" />
</template>

<script>
import FormularioPersona from './components/FormularioPersona.vue'
import HelloWorld from './components/HelloWorld.vue'
import TablaPersonas from './components/TablaPersonas.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    TablaPersonas,
    FormularioPersona
  },
  data(){
    return{
      personas: [
        {
          id: "100",
          nombre: "Michael Jordan", 
          equipo: "Chicago",
          correo: "michael@gmail.com"
        },
        {
          id: "200",
          nombre: "Bryan Scott", 
          equipo: "LA Lakers",
          correo: "bryan@gmail.com"
        },
        {
          id: "300",
          nombre: "Kevin Mchale", 
          equipo: "Celtics Boston",
          correo: "kevin@gmail.com"
        }

      ]//cierra array personas
    }//cierra return
  },//cierra data

  methods: {

agregarPersona(persona) {

let id = 0;

if (this.personas.length > 0) {

id = this.personas[this.personas.length - 1].id + 1;

}

this.personas= [...this.personas, { ...persona, id}];

}

}
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
