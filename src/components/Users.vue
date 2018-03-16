<template>
  <div class="users">
    <h1>Users page</h1>
    <ul class="users-list">
      <li v-for="(user,index) in users" v-bind:key="user.key">
        <div class="user-item">
          <div class="user-item-name">{{user.name}}</div>
          <div>
            <button type="button" v-on:click="deleteUser(index)">X</button>
          </div>
        </div>
      </li>
    </ul>

    <h2>Add a new user:</h2>
    <form v-on:submit="addUser">
      <div>
        <span>FirstName: </span>
        <input type="text" v-model="newUser.name"/>
      </div>
      <div>
        <span>Contacted</span>
        <input type="checkbox" name="contacted"  v-model="newUser.contacted"/>
      </div>
      <div>
        <span>Email</span>
        <input type="text" name="email"  v-model="newUser.email"/>
      </div>
      <input type='submit' value='Save user'>
    </form>

  </div>
</template>

<script>
export default {
  name: "users",

  data() {
    return {
      newUser: {
        key: "",
        name: "",
        contacted: false,
        email: ""
      },
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

  methods: {
    addUser: function(ev) {
      ev.preventDefault();
      this.users.push({
        key: this.users.length + 1,
        name: this.newUser.name,
        contacted: this.newUser.contacted,
        email: this.newUser.email
      });
    },
    deleteUser: function(userIndex) {
      console.log("user index", userIndex);
      this.users.splice(userIndex, 1);
    }
  }
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

.user-item {
  display: flex;
  justify-content: center;
  align-items: center;
}

.user-item-name {
  margin-right: 15px;
}
</style>

