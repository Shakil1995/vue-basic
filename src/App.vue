<template>
  <div>
    <!-- <h1>EmployeeTable app</h1> -->
    <EmployeeForm @add:employee="addEmployee" />
    <EmployeeTable :employees="employees" />
  </div>
</template>

<script>
import EmployeeForm from "./components/EmployeeForm.vue";
import EmployeeTable from "./components/EmployeeTable.vue";
export default {
  name: "App",
  data() {
    return {
      employees: [
        {
          id: 1,
          name: "shakil Nurul Amin",
          email: "shail.cse201@gmail.com",
        },
        {
          id: 2,
          name: " Nurul ",
          email: "shail.cse@gmail.com",
        },
        {
          id: 3,
          name: "Amin",
          email: "shail.01@gmil.com",
        },
      ],
    };
  },
  components: {
    EmployeeTable,
    EmployeeForm,
  },
  methods: {
    addEmployee(employee) {
      const lastID =
        this.employees.length > 0
          ? this.employees[this.employees.length - 1].id
          : 0;
      const id = lastID + 1;
      const newEmployee = { ...employee, id };
      this.employees = [...this.employees, newEmployee];
    },
  },
};
</script>

<style scoped></style>
