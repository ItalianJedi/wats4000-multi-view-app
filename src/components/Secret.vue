<template>
  <div class="secret">
    <h1>{{ message }}</h1>
    <img v-bind:src="image.src" v-bind:alt="image.title">
    <ul>
        <button><li><router-link v-bind:to="{ name: 'Home'}">Home</router-link></li></button>
        <button><li><router-link to="/survey">Survey</router-link></li></button>
        <button><li><router-link to="/about">About</router-link></li></button>
    </ul>   
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      message: "Always Make Sure To Drink Good Whiskey!",
      image: {
          src: "static/images/whiskey.jpg",
          title: "You deserve whiskey"
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.error {
  border: 1px solid #aa0000;
  padding: 1rem;
  color: #aa0000;
}
h1, h2 {
  font-weight: normal;
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
</style>
