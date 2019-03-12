
<template>
  <div class="students-details">
    <div class="card-header">
      <small class="text-muted">Students Details:</small>
    </div>
    <table class="table table-striped">
      <thead>
      <tr>
        <th scope="col">ID</th>
        <th scope="col">NAME</th>
        <th scope="col">CLASS</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="(student, index) in students" :key="index">
        <td>{{ student.studentId }}</td>
        <td>{{ student.studentName }}</td>
        <td>{{ student.studentClass }}</td>
        <td>
          <button class="btn btn-danger btn-sm" @click="remove(index)">x</button>
        </td>
      </tr>
      </tbody>
    </table>
    <p v-if="students.length === 0" class='text-center alert alert-warning'>No data found!</p>


    <!--{{students.length === 0 ? "No data found!" : ''}}-->
  </div>
</template>

<script>
  export default {
    props:["stdid", "stdname", "stdclass", "students"],
    methods: {
      remove(index) {
        this.$emit('remove', index)
      }
    },
  }
</script>