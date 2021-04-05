<template>
  <div class="body-container">
    <template v-if="pageData">
      <h1 class="project-title">{{ pageData.title }}</h1>
      
      <div class="project">
        <div class="project-content">
          <p v-html="pageData.description.context" />
        </div>
        
        <div class="project-illustrations">
          <img
            class="project-illustrations__image"
            v-for="(mediaUrl, key) in pageData.medias"
            :key="key"
            :src="mediaUrl"
            alt="">
        </div>
      </div>
    </template>
  </div>
</template>

<script>
import pages from '@/constants/pages';

export default {
  name : 'projet',
  data() {
    return {
      pageData : null
    }
  },
  beforeRouteEnter(to, from, next) {
    if (!pages.includes(to.params.name)) {
      next({ path: 'not-found' })
    } else {
      next()
    }
  },
  mounted() {
    fetch(`/project-data/${this.$route.params.name}.json`)
        .then(response => response.json())
        .then(response => {
          this.pageData = response
        })
  },
  watch: {
    '$route' (to) {
      fetch(`/project-data/${to.params.name}.json`)
        .then(response => response.json())
        .then(response => {
          this.pageData = response
        })
    }
  }
}
</script>