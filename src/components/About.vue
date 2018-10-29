<template>
  <div class="about">
    <h1>{{ message }}</h1>
    <hr>
    <p>{{ aboutUs }}</p>
    <img v-bind:src="image.src" v-bind:alt="image.title">
    <ul>
        <button><li><router-link v-bind:to="{ name: 'Home'}">Home</router-link></li></button>
    </ul>   
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      message: "About the Web Developers Club!",
      aboutUs: "Mixtape stumptown hammock vice craft beer keytar gluten-free plaid celiac beard asymmetrical fingerstache. Austin synth prism chia. 8-bit four loko mixtape kitsch, fanny pack four dollar toast hoodie shaman irony tacos kale chips freegan. Umami kinfolk echo park skateboard pabst copper mug. +1 disrupt meh, selvage freegan leggings green juice photo booth live-edge tote bag literally street art pickled.",
      image: {
          src: "static/images/wdc.jpg",
          title: "Web Developer Club"
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

img {
    height: 300px;
    weight: 300px;
}
</style>

