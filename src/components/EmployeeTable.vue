<template>
  <div id="employeez-table">
    <h1>this is tamplate page</h1>
    <table>
      <tr v-for="employee in employees" :key="employee.id">
        <td>{{employee.name}}</td>
          <td>{{employee.email}}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  naem: "Employee-table",
  props: {
    employees: Array,
  },
};
</script>

<style></style>
