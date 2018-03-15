<template>
  <div class="test">
    <span v-html="title">{{title}}</span>
    <p v-if="showName">{{user.firstName}}</p>
    <p v-else>Nobody</p>
    <ul class="items-list">
      <li v-for="item in items" v-bind:key="item.key">{{item.title}}</li>
    </ul>
    <p v-text="user.firstName"></p>
    <div>
      <input type="text" v-model="title">
    </div>
    <div>
      <button v-on:click="greet('wsp man')">Say hello</button>
    </div>
    <div>
      <input type="text" v-on:keyup="onPressKeyUp">
    </div>
    <div>
      <b>Receiving props:</b>
      <p>{{myCoolProp}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "test",

  props: {
    //my prop is called message
    myCoolProp: {
      type: String, // specify the type
      default: "Foobar" //set a default val
    }
  },

  data() {
    return {
      title: "<h2>Hello world</h2>",
      user: {
        firstName: "John",
        lastName: "Doe"
      },
      showName: false,
      items: [
        { title: "Item One", key: 0 },
        { title: "Item Two", key: 1 },
        { title: "Item Three", key: 2 }
      ]
    };
  },

  methods: {
    greet: greeting => {
      alert("Hey " + greeting);
    },
    onPressKeyUp: ev => {
      console.log("ev?", ev.target.value);
    }
  }
};
</script>

<style scoped>
.items-list {
  list-style-type: none;
  padding: 0;
  margin: 0;
}
.items-list li {
  padding: 10px 0;
}

div {
  margin-bottom: 10px;
}
</style>

