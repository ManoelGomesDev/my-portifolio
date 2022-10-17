<template>
  <v-col cols="12" md="3" align-self="center" >
    <v-img
      :src="require(`@/assets/${tech.image}`)"
      contain
      max-height="3.5rem"
     
    ></v-img>
    <p>{{ tech.name }}</p>
  </v-col>
</template>
<script>
export default {
  props: {
    tech: {
      type: Object,
    },
  },
};
</script>

<style scoped>
p {
    text-align: center;
}
</style>
