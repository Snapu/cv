<template>
  <v-card flat>
    <v-card-text>
      <div class="date">{{ date }}</div>
      <div class="job">
        <div><h4>{{ title }} @ {{ company }}</h4></div>
        <div class="job-description">
          <div>{{ description }}</div>
          <div v-if="technologies.length>0" class="job-technologies">
            <span>Technologies: </span>
            <span>{{ technologies.join(', ')}}</span>
          </div>
        </div>
      </div>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'JobItem',
  props: {
    date: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    company: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    technologies: {
      type: Array,
      required: true
    },
  }
}
</script>

<style scoped>
.job-description {
  border-left-style: solid;
  border-width: 0 0 0 1px;
  border-color: var(--v-primary-base);
  padding-left:3mm;
  font-size: small;
}
.date {
  color: grey;
}
.job-technologies {
  color: grey;
  font-size: small;
}
</style>

