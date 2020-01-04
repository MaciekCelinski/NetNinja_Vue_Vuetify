<template>
  <div class="home">
    <h1>Home Page</h1>
    <v-btn class="pink white--text m-2">Click Me</v-btn>
    <br />
    <br />
    <v-btn depressed color="pink">Click Me Again</v-btn>
    <br />
    <br />
    <v-btn text color="pink">Click Me Again and Again </v-btn>
    <br />
    <br />
    <v-btn depressed color="pink white--text">
      <v-icon left>mdi-email</v-icon>
      <span> Email me </span>
    </v-btn>
    <v-btn depressed small color="pink white--text">
      <v-icon left small>mdi-email</v-icon>
      <span> Email me </span>
    </v-btn>
    <v-btn depressed large color="pink white--text">
      <span> Email me </span>
      <v-icon right large>mdi-email</v-icon>
    </v-btn>
    <v-btn fab depressed small dark color="purple">
      <v-icon>mdi-heart</v-icon>
    </v-btn>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "home"
};
</script>
