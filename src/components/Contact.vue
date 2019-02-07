<template>
  <v-card flat class="contact-card">
    <v-card-title>
      <img src="../assets/myAvatar.jpg" class="avatar">
      <div class="content">
        <h1>{{ name }}</h1>
        <div>{{ address }}</div>
        <div>{{ tel }}</div>
        <div>{{ email }}</div>
        <div>{{ website }}</div>
        <div class="pt-3">
          <v-chip small color="primary" outline v-for="keyword in keywords" v-bind:key="keyword">{{ keyword }}</v-chip>
        </div>
      </div>
    </v-card-title>
  </v-card>
</template>

<script>
import KEYWORDS from '@/data/keywords.json'

export default {
  name: 'Contact',
  data() {
    return {
      name: process.env.VUE_APP_NAME,
      address: process.env.VUE_APP_ADDRESS,
      tel: process.env.VUE_APP_TEL,
      email: process.env.VUE_APP_EMAIL,
      website: process.env.VUE_APP_WEBSITE,
      keywords: KEYWORDS.keywords
    }
  }
}
</script>

<style scoped>
.contact-card {
  width: 100%; 
}
.avatar {
  margin-left: 1cm;
  width: 4cm;
  border-radius: 50%;
}
.content {
  margin-left: 1cm;
  max-width: 12.5cm;
}
</style>

