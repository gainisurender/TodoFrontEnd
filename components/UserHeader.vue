<template>
  <ul>
    <li><a href="#home">TodoApp</a></li>
    <li style="float: right">
      <nuxt-link to="/">Logout</nuxt-link>
    </li>

    <li style="float: right">
      <nuxt-link to="/CreateTodo">CreateTodo</nuxt-link>
    </li>

    <li style="float: right">
      <nuxt-link to="/GetAllTodos">AllTodos</nuxt-link>
    </li>

    <li style="float: right">
      <nuxt-link to="/Home">Home</nuxt-link>
    </li>
  </ul>
</template>

<script>
export default {
  name: "UserHeader",
};
</script>

<style scoped>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover:not(.active) {
  background-color: #111;
}

.active {
  background-color: #04aa6d;
}
</style>
