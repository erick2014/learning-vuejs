<template>
  <div class="users">
    <h1>Users page</h1>
    <ul class="users-list">
      <li v-for="user in users" v-bind:key="user.key">{{user.name}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "users",

  props: {},

  data() {
    return {
      users: [
        {
          key: 0,
          name: "Erick Garcia",
          contacted: false,
          email: "eagm.08@gmail.com"
        },
        {
          key: 1,
          name: "Natalia Higuita",
          contacted: false,
          email: "natybella@hotmail.com"
        },
        {
          key: 2,
          name: "Tom White",
          contacted: false,
          email: "tom@hotmail.com"
        }
      ]
    };
  },

  methods: {}
};
</script>

<style scoped>
.users-list {
  list-style-type: none;
  padding: 0;
  margin: 0;
}
.users-list li {
  padding: 10px 0;
}
</style>

