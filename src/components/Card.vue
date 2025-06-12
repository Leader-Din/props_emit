<template>
  <div class="card-container" v-if="user.length">
    <h2>Student List</h2>
    <div class="card" v-for="(person, index) in user" :key="index">
      <p><strong>ID:</strong> {{ person.id }}</p>
      <p><strong>Name:</strong> {{ person.fullName }}</p>
      <p><strong>Class:</strong> {{ person.class }}</p>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  user: Array
})
</script>

<style scoped>
.card-container {
font-family: 'Courier New', Courier, monospace;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 30px;
  max-width: 800px;
  margin: 50px auto;
  padding: 40px;
  background-color: #002f6c; /* Dark blue background */
  border-radius: 20px;
}

h2 {
  grid-column: 1 / -1;
  text-align: center;
  color: white;
  margin-bottom: 20px;
  font-size: 1.8em;
}

.card {
  background-color: #ffeb00; /* Bright yellow card */
  border-radius: 12px;
  padding: 30px 20px;
  text-align: center;
  font-size: 1.2rem;
  font-weight: bold;
  color: black;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  transition: transform 0.2s ease;
}

.card:hover {
  transform: scale(1.05);
}

.card p {
  margin: 10px 0;
  color: #000;
  font-weight: bold;
}


</style>
