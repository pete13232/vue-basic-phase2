<template>
  <h1>
    {{ message }}
  </h1>
  <ul>
    <Person
      v-for="item in employees"
      :id="item.id"
      :name="item.name"
      :salary="item.salary"
      :department="item.department"
      :isVisible="item.isVisible"
      @show="toggleVisible"
      @delete="removeEmployee"
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
        {
          id: 1,
          name: "ก้อง",
          salary: 40000,
          department: "โปรแกรมเมอร์",
          isVisible: false,
        },
        {
          id: 2,
          name: "แก้ม",
          salary: 30000,
          department: "ฝ่ายการตลาด",
          isVisible: false,
        },
        {
          id: 3,
          name: "โจโจ้",
          salary: 20000,
          department: "กราฟิก",
          isVisible: false,
        },
      ],
    };
  },
  methods: {
    toggleVisible(id) {
      this.employees = this.employees.map((item) => {
        if (item.id === id) {
          return { ...item, isVisible: !item.isVisible };
        }
        return item;
      });
    },
    removeEmployee(id) {
      this.employees = this.employees.filter((item) => {
        return item.id !== id;
      });
    },
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 1rem 0;
  padding: 0;
}
</style>
