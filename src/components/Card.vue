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
  width: 320px;
  margin: 0 auto;
  padding: 20px;
}

h2 {
  text-align: center;
  color: #333;
}

.card {
  background: #ffffff;
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 15px;
  margin-bottom: 15px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  transition: transform 0.2s;
}

.card:hover {
  transform: translateY(-3px);
}

.card p {
  margin: 4px 0;
}
</style>
