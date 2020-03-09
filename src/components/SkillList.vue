<template>
  <v-card flat>
    <v-card-text>
      <div>
        <div><h5>{{ category }}:</h5></div>
        <div>
          <v-chip small color="primary" outline v-for="skill in skills" :key="skill.name">
            {{ skill.name }}<v-icon right v-for="index in skill.level" :key="index">star_border</v-icon>
          </v-chip>
        </div>
      </div>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'SkillList',
  props: {
    category: {
      type: String,
      required: true
    },
    skills: {
      type: Array,
      required: true
    }
  }
}
</script>
