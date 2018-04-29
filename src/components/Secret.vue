<template>
  <div class="secret">
            <ol class="breadcrumb">
          <li class="breadcrumb-item">
            <router-link to="/">Home</router-link>
          </li>
          <li class="breadcrumb-item">
            <router-link to="/survey">Survey</router-link>
          </li>
          <li class="breadcrumb-item active">
            Secret
          </li>
        </ol>      
    <div class="container">
      <h1>{{ message }}</h1>
      <div class="row md-10">
        <div class="span4"></div>
        <div class="span4">
          <img class="center" v-for="img in images" v-bind:src="img" />
        </div>
        <div class="span4"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Secret',
  data () {
    return {
      images: ["https://i1.wp.com/blog.js-republic.com/wp-content/uploads/2017/03/whatelse.jpg?resize=1024%2C672"],
      message: 'Always check...'
    }
  },

}
</script>



