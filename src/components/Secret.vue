<template>
  <div class="secret">
            <ol class="breadcrumb">
          <li class="breadcrumb-item">
            <router-link to="/">Home</router-link>
          </li>
          <li class="breadcrumb-item active">
            Secret
          </li>
        </ol>  

    <!--TODO: Make this a meme -->    
    <h1>{{ message }}</h1>
    
  </div>


</template>


<script>
export default {
  name: 'Secret',
  data () {
    return {
      message: 'Always check your dev tools!'
    }
  },

}
</script>



