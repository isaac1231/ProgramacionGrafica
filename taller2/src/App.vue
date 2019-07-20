<template>
  <div id="app">
    <div>
      <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <a class="navbar-brand" href="#">Taller 2</a>
      </nav>
    </div>
    <div class="container">
      <div class="row mt-3">
        <div class="col-12 col-sm-4 col-lg-4 col-xl-4">
          <div class="form-group">
            <label for>Nombre y Apellido</label>
            <input
              required
              v-model="nombre"
              type="text"
              name
              id
              class="form-control"
              placeholder
              aria-describedby="helpId"
            />
          </div>
          <div class="form-group">
            <label for>Cédula/Pasaporte</label>
            <input
              required
              v-model="id"
              type="text"
              name
              id
              class="form-control"
              placeholder
              aria-describedby="helpId"
            />
          </div>
          <div class="form-group">
            <label for>Facultad</label>
            <input
              required
              v-model="facultad"
              type="text"
              name
              id
              class="form-control"
              placeholder
              aria-describedby="helpId"
            />
          </div>
          <div class="form-group">
            <label for>Sexo</label>
            <select class="form-control" v-model="sexo" required>
              <option value="" selected>Secciona un genero</option>
              <option value="F">F</option>
              <option value="M">M</option>
            </select>
          </div>
          <div class="form-group">
            <label for>Numero de computadora</label>
            <input
              required
              v-model="nPc"
              type="number"
              name
              id
              class="form-control"
              placeholder
              aria-describedby="helpId"
            />
          </div>
          <button class="btn btn-success" v-on:click="addUser">Agregar</button>
        </div>
        <div class="col-12 col-sm-8 col-lg-8 col-xl-8">
          <table class="table text-center">
            <thead>
              <tr>
                <th scope="col">Nombre</th>
                <th scope="col">Cédula/Pasaporte</th>
                <th scope="col">Facultad</th>
                <th scope="col">Sexo</th>
                <th scope="col">Número de Computadora</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item, index) in formUser" :key="index">
                <td>{{ item.nombre }}</td>
                <td>{{ item.id }}</td>
                <td>{{ item.facultad }}</td>
                <td>{{ item.sexo }}</td>
                <td>{{ item.nPc }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
export default {
  name: "App",
  components: {},
  data() {
    return {
      nombre: "",
      id: "",
      facultad: "",
      sexo: "",
      nPc: "",
      formUser: [
        {
          nombre: "",
          id: "",
          facultad: "",
          sexo: "",
          nPc: ""
        }
      ]
    };
  },
  methods: {
    addUser() {
      this.formUser.push({
        nombre:this.nombre,
        id:this.id,
        facultad:this.facultad,
        sexo:this.sexo,
        nPc:this.nPc
      });
      this.nombre='',
      this.id='',
      this.facultad='',
      this.sexo='',
      this.nPc=''
    }
  }
};
</script>

<style>
</style>
