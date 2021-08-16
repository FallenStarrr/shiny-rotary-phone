<template>

<form
  id="app"
  @submit="checkForm"
  action="https://vuejs.org/"
  method="post"
>
<h1>Войти</h1>

  <p v-if="errors.length">
    <b>Пожалуйста исправьте указанные ошибки:</b>
    <ul>
      <li v-for="error in errors" :key="error">{{ error }}</li>
    </ul>
  </p>

  <p>
    <label for="name" class="form-label">Имя</label>
    <input
      class="form-control"
      id="name"
      v-model="name"
      type="text"
      name="name"
    >
  </p>

  <p>
    <label for="pass" class="form-label">Пароль</label>
    <input
      class="form-control"
      id="pass"
      v-model="pass"
      type="password"
      name="pass"
     
    >
  </p>



  <p>
    <button
      @click="modal"
      type="submit"
      
       class="btn btn-primary"
    >Отправить </button>
  </p>

  <div class="modal" v-if="modal">
    <div class="modal__content">
      <h2>Modal</h2>
      <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Beatae eligendi rem nulla voluptatum. Magnam praesentium, ex sit nulla maiores nemo.</p>
    </div>
  </div>

</form>
 
</template>
    


<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },


  data() {
  return {
    errors: [],
    name: null,
    pass: null,
    modal: false
   
  }

 
},


 methods: {

    modal() {
     this.modal = !this.modal
    },
    checkForm(e) {
      if (this.name && this.age) {
        return true
      }


      this.errors = []


     
      if (!this.name) {
        this.errors.push('Требуется указать имя.');
      }
      if (!this.age) {
        this.errors.push('Требуется указать возраст.');
      }

      e.preventDefault(); 
    }
  }
}



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}


/* Form */

form {
  background:#42b983 ;
  display: flex;
  justify-content: center;
  flex-direction: column;
  width: 20%;
  margin: auto;
  border-radius: 5px;
}

input {
  color: rgb(252, 245, 245);
  margin-top: 10px;
  width: 60%;
  margin: auto;
  background: transparent;
  border: none;
  border-bottom: 2px black solid;

    appearance: none;
    -moz-appearance: none;
-webkit-appearance: none;
}

.btn {
  position: relative;
  top: 17px;
  width: 100%;
}

label {
  margin-right: 160px;
}

/* Modal */

.modal {
  width: 100%;
  height: 100%;
  background: rgb(187, 171, 171);
}


</style>
