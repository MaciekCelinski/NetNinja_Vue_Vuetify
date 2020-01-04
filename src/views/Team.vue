<template>
  <div class="team">
    <h1 class="subheading grey--text">This is a Team site</h1>
    <v-container class="my-5">
      <v-layout row wrap>
        <v-flex xs12 sm6 md4 lg3 v-for="member in team" :key="member.name">
          <v-card flat outlined class="text-center ma-2">
            <v-avatar class="mt-4" size="100">
              <v-img :src="member.avatar"></v-img>
            </v-avatar>
            <v-card-text>
              <div class="subheading p-2">{{member.name}}</div>
              <div class="grey--text">{{member.role}}</div>
            </v-card-text>
            <v-card-actions>
              <v-btn text color="grey">
                <v-icon small left>mdi-message</v-icon>
                <span>MESSAGE</span>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      team: [
        {
          name: "The Net Ninja",
          role: "Web developer",
          avatar: "/avatar-1.png"
        },
        { name: "Ryu", role: "Graphic designer", avatar: "/avatar-2.png" },
        { name: "Chun Li", role: "Web developer", avatar: "/avatar-3.png" },
        {
          name: "Gouken",
          role: "Social media maverick",
          avatar: "/avatar-4.png"
        },
        { name: "Yoshi", role: "Sales guru", avatar: "/avatar-5.png" }
      ]
    };
  }
};
</script>

<style>
</style>