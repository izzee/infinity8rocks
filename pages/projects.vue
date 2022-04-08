<template>
  <div class="page-content">
    <ProjectsSection 
      v-for="(project, index) in projects" 
      :project="project" 
      :key="index"
    />
  </div>
</template>

<script>
  import projects from 'static/data/projects.json' 
  export default {
    asyncData () {
      return { projects }
    },
    head() {
      return {
        script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }],
      };
    },
  };
</script>
