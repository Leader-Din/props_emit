<template>
  <div class="form-container">
    <h2>Student Registration</h2>

    <label for="fullname">Full Name</label>
    <input v-model="inputFullName" type="text" placeholder="Enter full name" />

    <label for="id">ID</label>
    <input v-model="inputId" type="number" placeholder="Enter student ID" />

    <label for="class">Class</label>
    <input v-model="inputClass" type="text" placeholder="Enter class name" />

    <button @click="addToCard">Add Student</button>
  </div>
</template>

<script setup>

/**
 * 
 * import ref from vue
 * 
 */

import { ref } from 'vue'

/**
 * 
 * create emit​ variable
 * 
 */

const emit = defineEmits(['submitStudent'])

/**
 * de clear variable 
 */

const inputFullName = ref('')
const inputId = ref('')
const inputClass = ref('')

/**
 * function add data to from form to array
 */

const addToCard = () => {

  /**
   * 
   * Check value in form if have sent to array
   * 
   */

  if (inputFullName.value && inputId.value && inputClass.value) {
    emit('submitStudent', {
      id: inputId.value,
      fullName: inputFullName.value,
      class: inputClass.value
    })

    /**
     * 
     * use for clear form when submit already
     * 
     */

    inputFullName.value = ''
    inputId.value = ''
    inputClass.value = ''

    /**
     * 
     * if don't have value alert to the user
     * 
     */
    
  } else {
    alert('Please fill in all fields.')
  }
}
</script>

<style scoped>
.form-container {
  background: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 12px;
  padding: 20px;
  width: 320px;
  margin: 20px auto;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.form-container h2 {
  text-align: center;
  color: #333;
}

input {
  padding: 10px;
  font-size: 14px;
  border-radius: 6px;
  border: 1px solid #ccc;
}

button {
  padding: 10px;
  font-size: 16px;
  background-color: #3f51b5;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #303f9f;
}
</style>
