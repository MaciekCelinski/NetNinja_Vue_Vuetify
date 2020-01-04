<template>
  <div class="home">
    <h1>Home Page</h1>
    <v-btn class="d-sm-none d-md-flex">Click Me</v-btn>
    <br />
    <v-btn class="hidden-sm-and-down">Click Me</v-btn>
    <br />
    <v-btn class="hidden-md-only">Click Me</v-btn>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "home"
};
</script>
