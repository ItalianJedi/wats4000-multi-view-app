<template>
  <div class="home">
    <div v-show="showForm" class="form-container">
      <h1>Join the Web Developers Club!</h1>
      <hr>
      <p>Sign up today for access our special, secret page! Just create an account and answer a brief survey.</p>
      <ul>
          <button><li><router-link v-bind:to="{ name: 'About'}">About Us</router-link></li></button>
       </ul>  

      <p v-show="showError" class="error">You are missing information in the fields. Please double check to make sure all fields are filled out.</p>

      <form v-on:submit.prevent="validateForm">

        <fieldset>

          <legend>Sign Up!</legend>

        <p><label for="username">
          <input type="text" id="username" v-model="username" placeholder="Enter Username">
        </label></p>

        <p><label for="email">
          <input type="email" id="email" v-model="email" placeholder="you@example.com">
          </label></p>

        <p><label for="password">
          <input type="password" id="password" v-model="password" placeholder="Enter Your Password">
          </label></p>
        <p>{{ password }}</p>

        <p><label for="passwordVerify">
          <input type="password" id="passwordVerify" v-model="passwordVerify" placeholder="Enter Your Password Again">
          </label></p>
        <p>{{ passwordVerify }}</p>

        <p>How did you discover us?<br>
          <label v-for="discover in discoverUs">
            <input type="checkbox" v-model="discoverUs" v-bind:value="discover.value">
            {{ discover.text }}
          </label>
        </p>

        <p><label for="stateChooser">State:</label>
           <select v-model="stateSelection">
              <option disabled value="">Please select one</option>
              <option v-for="state in stateList" v-bind:value="state">{{ state }}</option>
           </select>
        </p>
        </fieldset>

        <p><input type="submit" value="Submit"></p>
      </form>
    </div>
    <div v-show="!showForm" class="success-message">
      <h1>Thank you for signing up!</h1>
      <img v-bind:src="image.src" v-bind:alt="image.title">
      <p>Please take our new member survey. <router-link to="Survey">Click here</router-link></p>
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
      image: {
          src: "static/images/owl.jpg",
          title: "Web Dev Owl"
      },
      discoverUs: [
        {
          text: 'Newspaper',
          value: 'newspaper'
        },
        {
          text: 'Radio',
          value: 'radio'
        },
        {
          text: 'Word of Mouth',
          value: 'word'
        },
        {
          text: 'Shawn Rider',
          value: 'shawn'
        },
        {
          text: 'Other',
          value: 'other'
        }
      ],
      stateList: [
        'WA',
        'OR',
        'NY'
      ],
      stateSelection: 'WA'
    }
  },
  methods: {
    validateForm: function () {
      if ((this.username != '') &&
          (this.email != '') &&
          (this.password === this.passwordVerify) &&
          (this.discover === 'newspaper' || 'radio' || 'word' || 'shawn' || 'other')){
        console.log('Form is valid');
        this.showForm = false;
      } else {
        console.log('Form is not valid');
        this.showError = true;
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
