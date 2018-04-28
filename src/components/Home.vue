<template>
  <div class="home">
            <ol class="breadcrumb">
          <li class="breadcrumb-item">
            Home
          </li>
        </ol>  
    
    
    <div v-show="showForm" class="form-container container card bg-info text-white mb-3">
      <h1 class="card-header">Join the Web Developers Club!</h1>
      <p>Sign up to access our special, secret page. Just create an account and answer a brief survey.</p>
      
      <p id="error" v-show="showError" class="">Dag! You broke it!</p>

      <form v-on:submit.prevent="validateForm">

        <p>
          <label for="username">Usernames
            <input class="form-control mr-sm-2" type="text" id="username"v-model="username">
          </label>
        </p>
        <p>
          <label for="email">Email
            <input class="form-control mr-sm-2" type="email" id="email" v-model="email">
          </label>
        </p>
        <p>
          <label for="password">Password
            <input class="form-control mr-sm-2" type="password" id="password" v-model="password">
          </label>
        </p>
        <p>
          <label for="passwordVerify">Verify Password
            <input class="form-control mr-sm-2" type="password" id="passwordVerify" v-model="passwordVerify">
          </label>
        </p>
        <p><input class="btn btn-primary" type="submit" value="Submit"></p>
      </form>
    </div>
    
    <!--TODO: Make this a modal -->
    <div v-show="showModal" class="container card bg-info text-white mb-3">
      <div class="card-header"><h3>Thank you for signing up!</h3></div>
      <div class="card-body">
      <p class="card-text">Please take our new member survey.<br><br><router-link to="Survey" class="btn btn-warning btn-md text-white" type="button">Click here</router-link></p>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      username: '',
      email: '',
      password: '',
      passwordVerify: '',
      showForm: true,
      showError: false,
      showModal: false
    }
  },
  methods: {
    validateForm: function () {
      if ((this.username !== '') && 
      (this.email !== '') &&
      (this.password === this.passwordVerify)) {
        console.log("Form is valid");
        // TODO: Assign bootstrap success class to div instead
        this.showForm = false;
        this.showModal = true;
      } else {
        this.showForm = true;
        // TODO: Assign bootstrap error class to div instead
        this.showError = true;
        console.log("Form is not valid");
      }
    },

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
