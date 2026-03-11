<script setup>
import { ref, onMounted } from 'vue';

  const message = ref('Hello Vue!');
  const status = ref('active');
  const tasks = ref(['Learn JavaScript', 'Learn Vue', 'Build something awesome']);
  const newTask = ref('');

  const toggleStatus = () => {
    if (status.value === 'active') {
      status.value = 'pending';
    } else if (status.value === 'pending') {
      status.value = 'inactive';
    } else {
      status.value = 'active';
    }
  };

  const addTask = () => {
    if (newTask.value.trim() !== '') {
      tasks.value.push(newTask.value.trim());
      newTask.value = '';
    }
  };

  const deleteTask = (index) => {
    tasks.value.splice(index, 1);
  };

  onMounted(async () => {
    try {
      const response = await fetch('https://jsonplaceholder.typicode.com/todos');
      const data = await response.json();
      tasks.value = data.map((task) => task.title); // Assuming the API returns an array of tasks with a 'title' property
      // console.log('Fetched data:', data);
    } catch (error) {
      console.error('Error fetching data:', error);
    }
  });

// export default {
//   setup() {
//     const message = ref('Hello Vue!');
//     const status = ref('active');
//     const tasks = ref(['Learn JavaScript', 'Learn Vue', 'Build something awesome']);

//     const toggleStatus = () => {
//       if (status.value === 'active') {
//         status.value = 'pending';
//       } else if (status.value === 'pending') {
//         status.value = 'inactive';
//       } else {
//         status.value = 'active';
//       }
//     }

//     return {
//       message,
//       status,
//       tasks,
//       toggleStatus
//     };
//   }
// };
</script>

 
<template>
  <h1>{{ message }}</h1>
  <p v-if="status === 'active'">User is active!</p>
  <p v-else-if="status === 'pending'">User is pending!</p>
  <p v-else>User is inactive!</p>

  <form @submit.prevent="addTask">
    <label for="newTask">Add Task:</label>
    <input type="text" id="newTask" name="newTask" v-model="newTask">
    <button type="submit">Add</button>
  </form>

  <h3>Tasks:</h3>
  <ul>
    <li v-for="(task, index) in tasks" :key="task">
      <span>{{ task }}</span>
      <button @click="deleteTask(index)">Delete</button>
    </li>
  </ul>


   <br>
   <!-- <button @click="updateMessage">Click me</button> -->
    <button v-on:click="toggleStatus">Click me</button>
</template>

<!-- <style scoped>
h1 {
  color: #42b983;
}
</style> -->
