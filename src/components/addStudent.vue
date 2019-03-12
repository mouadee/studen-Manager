<template>
    <div class="card">
        <div class="card-header">
            <small class="text-muted">Add Students:</small>
        </div>
        <div class="card-body">
            <div class="form-group">
                <label class="mr-4" for="id">ID</label>
                <input v-model="studentId" type="text" id="id" placeholder="Student ID">
                <label class="mr-4 ml-4" for="name">Name</label>
                <input v-model="studentName" type="text" id="name" placeholder="student Name">
                <label class="mr-4 ml-4" for="className">Class</label>
                <input v-model="studentClass" type="text" id="className" placeholder="student Class">
                <button class="btn btn-success ml-4" @click="addStudent()">Add</button>
            </div>
        </div>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                studentId: '',
                studentName: '',
                studentClass:''
            }
        },
        methods: {
            addStudent() {
                if (this.studentId!== '' && this.studentName!== '' && this.studentClass!== '' ) {
                    this.$emit('addStudent', {studentId: this.studentId, studentName: this.studentName, studentClass: this.studentClass});
                } else {
                    alert('Please fill out all the fields !')
                }
                this.studentId = "";
                this.studentName = "";
                this.studentClass = "";
            }
        },
    }
</script>
