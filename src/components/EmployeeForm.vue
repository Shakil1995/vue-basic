<template>
    <div id="employee-form">
<form @submit.prevent="handleEmployee" >
    <label class="form-control" >Employee Name</label> <br>
    <input  type="text" v-model="employee.name" /> <br>
     <label for="">Employee Mail</label> <br>
    <input type="text"  v-model="employee.email" /> <br>
    <button>Add Employee</button>
</form>
    </div>
</template>

<script>
    export default {
    name:"Employee-form",
    data() {
        return {
            employee:{
                name:"",
                email:"",
            }
        }
    },
   methods: {
      handleEmployee(){
            this.$emit('add:employee', this.employee)
    }
   },
    }
</script>

<style lang="scss" scoped>

</style>