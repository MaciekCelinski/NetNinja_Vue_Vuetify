<template>
  <div class="home">
    <h1 class="subheading grey--text">Dashboard</h1>

    <v-container class="my-5">

      <v-layout row class="mb-3">
        <v-tooltip top>
          <template v-slot:activator="{ on }">
          <v-btn class="mr-3" small depressed color="light-grey" @click="sortBy('title')" v-on="on">
            <v-icon color="grey" left small>mdi-folder</v-icon>
            <span class="caption text-lowercase grey--text">By project name</span>
          </v-btn>
          </template>
          <span>Sort by Project</span>
        </v-tooltip>
        
                <v-tooltip top>
          <template v-slot:activator="{ on }">
        <v-btn small depressed color="light-grey" @click="sortBy('person')" v-on="on"> 
          <v-icon color="grey" left small>mdi-account</v-icon>
          <span class="caption text-lowercase grey--text">By person</span>
        </v-btn>
                  </template>
          <span>Sort by Person</span>
        </v-tooltip>
      </v-layout>

      <v-card flat v-for="project in projects" :key="project.title">
        <v-layout row wrap :class="`pa-3 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text">Project Title</div>
            <div>{{project.title}}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Person</div>
            <div>{{project.person}}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Due by</div>
            <div>{{project.due}}</div>
          </v-flex>
          <v-flex xs2 sm4 md2>
            <div class="text-right mr-3">
              <v-chip
                small
                :class="` ${project.status} white--text caption my-3`"
              >{{project.status}}</v-chip>
            </div>
          </v-flex>
        </v-layout>
        <v-divider></v-divider>
      </v-card>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "home",
  data() {
    return {
      projects: [
        {
          title: "Design a new Website",
          person: "Maciek Celiński ",
          due: "1st Jan 2011",
          status: "complete"
        },
        {
          title: "Code up the homepage",
          person: "Net Ninja",
          due: "13th Sep 2014",
          status: "ongoing"
        },
        {
          title: "Design video thumbnails",
          person: "Brad Traversy",
          due: "2nd March 2017",
          status: "overdue"
        },
        {
          title: "Create a community forum",
          person: "Chuck Lorre",
          due: "21th Jul 2019",
          status: "decline"
        }
      ]
    };
  },
  methods: {
    sortBy(prop) {
      this.projects.sort((a, b) => (a[prop] < b[prop] ? -1 : 1));
    }
  }
};
</script>

<style scoped>
.project.complete {
  border-left: 4px solid #3cd1c2;
}
.project.ongoing {
  border-left: 4px solid orange;
}
.project.overdue {
  border-left: 4px solid tomato;
}
.project.decline {
  border-left: 4px solid grey;
}
.v-chip.complete {
  background-color: #3cd1c2 !important;
}
.v-chip.ongoing {
  background: #ffaa2c !important ;
}
.v-chip.overdue {
  background: #f83e70 !important ;
}
.v-chip.decline {
  background: grey !important;
}
</style>