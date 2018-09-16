<template>
  <ul class="student-list">
  <li class="student-item cf" v-for="(student, i) in students">
  <div class="student-details">
  <img class="avatar" :src="student.src">
  <h3>{{student.name}}</h3>
  <span class="email">{{student.email}}</span>
  </div>
  <div class="joined-details">
  <span class="date">{{student.date}}</span>
  </div>
  </li>
  </ul>

</template>

<script>
export default {
  name: 'Students',
  props: {
    students: Array,
  },

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
