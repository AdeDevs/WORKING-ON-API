<template>
  <div class="container">
    <h1>{{ title }}</h1>
    <p>{{ msg }} {{ name }}</p>
    <slot />
    <button @click="getData()">{{ text }}</button>
  </div>
  <div>
    <img :src="avatar" alt="" />
    <p>{{ firstName }} {{ lastName }}</p>
    <p>{{ email }}</p>
  </div>
</template>

<script>
export default {
  name: "HomePage",
  props: ["title", "msg", "name"],
  data() {
    return {
      text: "Fetch",
      firstName: "Ibrahim",
      lastName: "Alani",
      email: "jondoe@gmail.com",
      avatar: "https://randomuser.me/api/portraits/men/19.jpg",
    };
  },
  methods: {
    async getData() {
      const res = await fetch("https://randomuser.me/api/");
      const { results } = await res.json();
      // console.log(results);

      this.firstName = results[0].name.first;
      this.lastName = results[0].name.last;
      this.email = results[0].email;
      this.avatar = results[0].picture.large;
    },
  },
};
</script>

<style>
@import "./styles.app.css";
button {
  border: 2px solid black;
  padding: 5px 20px;
  border-radius: 5px;
  margin-bottom: 10px;
}
button:hover {
  background-color: black;
  border: 2px solid red;
  color: white;
  transition: 300ms;
}
img {
  border-radius: 50%;
}
</style>