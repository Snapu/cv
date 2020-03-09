<template>
  <v-card flat>
    <v-card-text>
      <div class="school">
        <div><h4>{{ degree }}</h4></div>
        <div>{{ name }}</div>
        <div class="school-date">{{ date }}</div>
      </div>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'SchoolItem',
  props: {
    degree: {
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    date: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
.school-date {
  color: grey;
}
</style>

