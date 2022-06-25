<template>
  <h1>
    {{ message }}
  </h1>
  <ul>
    <Person
      v-for="item in employees"
      :key="item.id"
      :name="item.name"
      :salary="item.salary"
      :department="item.department"
      :isVisible="item.isVisible"
    />
  </ul>
</template>

<script>
import Person from "./Person.vue";
export default {
  name: "ListData",
  components: {
    Person,
  },
  data() {
    return {
      employees: [
        { id:1, name: "ก้อง", salary: 40000, department:"โปรแกรมเมอร์", isVisible:false},
        { id:2, name: "แก้ม", salary: 30000, department:"ฝ่ายการตลาด", isVisible:false},
        { id:3, name: "โจโจ้", salary: 20000, department:"กราฟิก", isVisible:false},
      ],
    };
  },
};
</script>

<style scoped>
ul{
  list-style: none;
  margin: 1rem 0;
  padding: 0;
}
</style>
