<template>
  <div class="container">
    <UserHeader />
    <div>
      <table align="center">
        <tr v-for="(todo, i) in $store.state.todos" :key="i">
          <td>{{ i + 1 }}</td>
          <td>{{ todo.description }}</td>
          <td>{{ todo.isCompleted }}</td>
        </tr>
        <tr></tr>
      </table>
    </div>
  </div>
</template>

<script>
import UserHeader from "../components/UserHeader.vue";
export default {
  computed: { UserHeader },
  data() {
    return {
      errorMsg: "",
    };
  },
  async mounted() {
    await this.$store.dispatch("getTodos");
    return;
  },
};
</script>

<style>
#customers {
  font-family: Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

#customers td,
#customers th {
  border: 1px solid rgb(200, 225, 243);
  padding: 8px;
}

#customers tr:nth-child(even) {
  background-color: #aecbef;
}

#customers tr:hover {
  background-color: rgb(205, 229, 239);
}

#customers th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  background-color: #04aa6d;
  color: white;
}
h1 {
  display: flex;
  text-align: center;
  color: rgb(59, 59, 138);
}
</style>