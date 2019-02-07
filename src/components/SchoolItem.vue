<template>
  <v-card flat class="school-item-card">
    <v-card-text>
      <div class="school">
        <div><h4><slot name="degree"></slot></h4></div>
        <div><slot name="name"></slot></div>
        <div class="school-date"><slot name="date"></slot></div>
      </div>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'SchoolItem'
}
</script>

<style scoped>
.school-item-card {
  width: 100%; 
}
.school-date {
  color: grey;
}
</style>

