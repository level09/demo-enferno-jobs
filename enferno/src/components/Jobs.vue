<template>
    <section class="text-gray-700 body-font overflow-hidden">
  <div class="container px-5 py-24 mx-auto">
    <div class="-my-8">
      <div v-for="job in jobs" class="py-8 flex flex-wrap md:flex-no-wrap">
        <div class="md:w-64 md:mb-0 mb-6 flex-shrink-0 flex flex-col">
          <span class="tracking-widest font-medium title-font text-gray-900">{{job.tags[0]}}</span>
          <span class="mt-1 text-gray-500 text-sm">{{job.date.split('T')[0]}}</span>
        </div>
        <div class="md:flex-grow">
          <h2 class="text-2xl font-medium text-gray-900 title-font mb-2">{{job.position}}</h2>
          <p class="leading-relaxed">{{job.description}}</p>
          <a :href="job.url" target="_blank" class="text-indigo-500 inline-flex items-center mt-4">Apply now on RemoteOk
            <svg class="w-4 h-4 ml-2" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round">
              <path d="M5 12h14"></path>
              <path d="M12 5l7 7-7 7"></path>
            </svg>
          </a>
        </div>
      </div>

    </div>
  </div>
</section>
</template>
<script>
  import axios from 'axios';
  export default {

    data: function() {
      return {
        jobs: []
      }
    },
    mounted () {
      axios.get('/api').then(res =>{
        let jobs = res.data;
        // remove first legal item
        jobs.splice(0,1);

      this.jobs = jobs;
      })
    }
  }
</script>