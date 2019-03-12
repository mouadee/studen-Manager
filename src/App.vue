
<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 mt-4 text-center">
          <addStudent @addStudent="addStudent($event)">
          </addStudent>
        </div>
        <div class="col-lg-12 mt-4 text-center">
          <studentDetails
                  :stdid="studentId"
                  :stdname="studentName"
                  :stdclass="studentClass"
                  :students="students"
                  @remove="remove($event)"
          ></studentDetails>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import studentDetails from './components/studentDetails.vue'
  import addStudent from './components/addStudent.vue'

  export default {
    name: 'app',
    components: {
      studentDetails, addStudent
    },
    data() {
      return {
        studentId: '', studentName: '', studentClass: '',
        students: [
          {studentId: 0,studentName: 'Name 1', studentClass: 'Class 1'},
          {studentId: 1,studentName: 'Name 2', studentClass: 'Class 2'},
          {studentId: 2,studentName: 'Name 3', studentClass: 'Class 3'}
        ]
      }
    },
    methods: {
      addStudent(data){
        this.students.push(data)
      },
      remove(index){
        this.$delete(this.students, index)
      }
    },
  }
</script>

