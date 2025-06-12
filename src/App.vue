<template>
  <StudentForm @submitStudent="addStudent" />
  <Card :user="students" />
</template>

<script setup>
import { ref } from "vue";
import StudentForm from "./components/StudentForm.vue";
import Card from "./components/Card.vue";

const students = ref([]);

const addStudent = (student) => {
  students.value.push(student);
};
</script>
