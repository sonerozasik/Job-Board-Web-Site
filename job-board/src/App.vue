<template>
  <div class="container">
    <h1 class="text-center">Jobs</h1>
    <div class="form-group">
      <input type="text" class="form-control" v-model="keyword" placeholder="Search jobs by keyword..." />
    </div>
    <div class="form-group">
      <input type="text" class="form-control" v-model="location" placeholder="Search jobs by  location..." />
    </div>
    <jobs-list :jobs="filteredJobs" />
  </div>
  
</template>

<script>
import JobsList from './components/JobsList.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    JobsList
  },
  data() {
    return {
      keyword: '',
      location: '',
      jobs: [ ]
    }
  },
  computed: {
    filteredJobs() {
      return this.jobs.filter(job => job.title.toLowerCase().includes(this.keyword.toLowerCase()) && job.location.toLowerCase().includes(this.location.toLowerCase()))
    }
  },
  created() {
    axios.get('/jobs.json').then(response => {
      this.jobs = response.data
    })
  }
}
</script>