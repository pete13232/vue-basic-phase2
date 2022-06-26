<template>
  <h1>
    {{ message }}
  </h1>
  <ul>
    <Person
      v-for="(item,index) in employees"
      :name="item.name"
      :salary="item.salary"
      :department="item.department"
      :gender="item.gender"
      :skill="item.skill"
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
  props: ["employees"]
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 1rem 0;
  padding: 0;
}
</style>
