<template>
  <div>
    <h1>function call</h1>

    <h2>{{ name }}</h2>

    <button @click="changename">change name</button>
  </div>
</template>

<script>
export default {
  name: "HomeCom",

  data() {
    return {
      name: "My name is nikita",
    };
  },

  methods: {
    changename() {
      this.name = "My name is nikky";
    },
  },
};
</script>

<style>
h1 {
  text-align: center;
}
</style>
