<template>
  <div class="secret">
    <h1>{{ message }}</h1>

    <ul>
      <!--TODO: Figure out why text is not white?-->
      <li type="button" class="text-white btn btn-info btn-lg"><router-link v-bind:to="{ name: 'Home' }">Home</router-link></li>
      <li type="button" class="btn btn-warning btn-lg"><router-link to="/survey">Survey</router-link></li>
    </ul>
    
  </div>


</template>


<script>
export default {
  name: 'Home',
  data () {
    return {
      message: 'Always check your dev tools!'
    }
  },

}
</script>



