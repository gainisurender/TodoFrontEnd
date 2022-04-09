<template>
  <div class="container">
    <UserHeader />
    <div>
      <table align="center">
        <tr v-for="(todo, i) in $store.state.mytodos" :key="i">
          <td>{{ i + 1 }}</td>
          <td>{{ todo.description }}</td>
          <td>{{ todo.isCompleted }}</td>
          <td>
            <button @click="updateTodo(todo.id)">UPDATE</button>
          </td>
          <td>
            <button @click="deleteTodo(todo.id)">DELETE</button>
          </td>
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
    await this.$store.dispatch("getMyTodos");
    return;
  },

  methods: {
  async  deleteTodo(id) {
      console.log(id);
     await this.$store.dispatch("deleteTodo", id);
    },

   async updateTodo(id) {
      console.log(id);
    await  this.$store.dispatch("updateTodo", id);
    },
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