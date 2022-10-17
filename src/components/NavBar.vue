<template>
    <v-app-bar flat color="white" max-height="100" align="center" tile>
    <v-row >
        <v-col cols="12" md="4">
            <h3>Logo</h3>
        </v-col>
      <v-spacer></v-spacer>
      
      <v-col cols="12" md="4" >
        <a class="mr-3" v-scroll-to="{ element: '#skill', duration: 3000 }">Skills</a>
        <a class="mr-3" v-scroll-to="{ element: '#project', duration: 3000 }">Projects</a>
        <a class="mr-3" v-scroll-to="{ element: '#contact', duration: 3000 }">Contact-me</a>
      </v-col>
    </v-row>
  </v-app-bar>
</template>
