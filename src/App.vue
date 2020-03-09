<template>
  <v-app id="app">
    <v-content>
      <v-container fluid class="page">
        <v-layout row wrap>
            <v-flex xs12>
              <contact/>
            </v-flex>
            <v-flex xs12 md8>
              <div class="section-headline">
                <v-icon color="primary">work</v-icon>
              </div>
              <job-item v-for="job in jobs" :key="job.title"
                :date="job.date"
                :title="job.title"
                :company="job.company"
                :description="job.description"
                :technologies="job.technologies"/>
            </v-flex>
            <v-flex xs12 md4>
              <div class="section-headline">
                <v-icon color="primary">school</v-icon>
              </div>
              <school-item v-for="school in schools" :key="school.degree"
                :degree="school.degree"
                :name="school.name"
                :date="school.date"/>
              <div class="section-headline">
                <v-icon color="primary">star</v-icon>
              </div>
              <skill-list v-for="skillList in skillLists" :key="skillList.category"
                :skills="skillList.skills"
                :category="skillList.category"/>
            </v-flex>
            <v-flex xs12>
              <p class="last-updated">last updated: {{ lastUpdated }}</p>
            </v-flex>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import Contact from './components/Contact'
import JobItem from './components/JobItem'
import SchoolItem from './components/SchoolItem'
import SkillList from './components/SkillList'
import JOBS from './data/jobs.json'
import SCHOOLS from './data/schools.json'
import SKILL_LISTS from './data/skillLists.json'
import LAST_UPDATED from './data/lastUpdated.json'

export default {
  name: 'App',
  components: {
    Contact,
    JobItem,
    SchoolItem,
    SkillList
  },
  data() {
    return {
      jobs: JOBS.jobs,
      schools: SCHOOLS.schools,
      skillLists: SKILL_LISTS.skillLists,
      lastUpdated: LAST_UPDATED.lastUpdated
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.page {
  width: 21cm;
  height: 29.7cm;
  background-color: white;
  padding: 0 16px 0 32px;
}
.section-headline {
  padding-top: 5mm;
  padding-left: 16px;
}
.last-updated {
  color: gray;
  font-size: small;
  text-align: center;
}
</style>
