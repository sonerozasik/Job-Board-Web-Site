<template>
    <ul class="list-group">
        <div class="row g-0">
            <li v-for="job in jobs" :key="job.title" class="list-group-item col-md-6 text-center">
                <h2 class="h5">{{ job.title }}</h2>
                <p class="text-muted">{{ job.company }}</p>
                <p class="text-muted">{{ job.location }}</p>
                <p>{{ job.description }}</p>
                <button class="btn btn-primary" @click="showModal = true">Apply</button>
              </li>
        </div>
      </ul>
      
  </template>
  
  <script>

  export default {
    name: 'JobsList',
    components: {
    }, 
    data() {
        return {
    }
  },
    props: {
      jobs: {
        type: Array,
        required: true
      }
    },
    methods: {

  }
  }
  </script>

  <style>

</style>