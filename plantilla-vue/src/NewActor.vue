<template>
  <div class="center">
    <h2>{{title}}</h2>

      <p>
        <label for="firstName">Nombre</label>
        <input type="text" id="firstName" name="firstName" required v-model="actor.firstName" onClick="this.select();" >
      </p>
      <p>
        <label for="lastName">Apellido</label>
        <input type="text" id="lastName" name="lastName" required v-model="actor.lastName" onClick="this.select();" >
      </p>
      <p><button v-on:click="addActor()"  >Agregar Actor</button></p>



  </div>
</template>

<script>
  export default {
    data(){
      return{
        title:'Agregar actor',
        actor:{firstName:'',lastName:''}
      }
    },
    methods:{
      addActor:function(){
        if (firstName.value == 0 && lastName.value == 0){
          alert("Tus campos no fueron llenados");
        }
        else if (firstName.value == 0){
          alert("Favor Llenar Campo de Nombre");
        }
        else if (lastName.value == 0){
          alert("Favor Llenar Campo Apellido");
        }
        else{

              this.$http.post('http://localhost:8080/TBDTaller1/actors', this.actor);
              alert("Actor Creado");


          }
        }
      }
    }
</script>
