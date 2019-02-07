<template>
  <v-card flat class="job-item-card">
    <v-card-text>
      <div class="date">
        <slot name="date"></slot>
      </div>
      <div class="job">
        <div><h4><slot name="title"></slot></h4></div>
        <div class="job-description">
          <slot name="description"></slot>
          <div class="job-technologies">
            <span v-if="technologies.length>0">Technologies: </span>
            <template v-for="(technology, index) in technologies">
              <span v-if="index<technologies.length-1" :key="index">{{ technology }}, </span>
              <span v-else :key="index">{{ technology }}.</span>
            </template>
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
    technologies: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
.job-item-card {
  width: 100%;
}
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

