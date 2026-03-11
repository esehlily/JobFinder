<script>
export default {
  data() {
    return {
      message: 'Hello Vue!',
      status: 'active',
      tasks: ['Learn JavaScript', 'Learn Vue', 'Build something awesome'],
      link: 'https://vuejs.org'
    };
  },
  methods: {
    // You can add methods here if needed
    // updateMessage() {
    //   this.message = 'You clicked the button!';
    // }
    toggleStatus() {
      // this.status = this.status === 'active' ? 'pending' : 'active';
      if (this.status === 'active') {
        this.status = 'pending';
      } else if (this.status === 'pending') {
        this.status = 'inactive';
      } else {
        this.status = 'active';
      }
    } 
  }
};
</script>

 
<template>
  <h1>{{ message }}</h1>
  <p v-if="status === 'active'">User is active!</p>
  <p v-else-if="status === 'pending'">User is pending!</p>
  <p v-else>User is not active!</p>

  <h3>Tasks:</h3>
  <ul>
    <li v-for="task in tasks" :key="task">
      {{ task }} 
    </li>
  </ul>

  <!-- <a v-bind:href="link" target="_blank">Visit Vue.js</a> -->
   <a :href="link" target="_blank">Visit Vue.js </a>

   <br>
   <!-- <button @click="updateMessage">Click me</button> -->
    <button v-on:click="toggleStatus">Click me</button>
</template>

<!-- <style scoped>
h1 {
  color: #42b983;
}
</style> -->