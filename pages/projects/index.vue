<template>
  <div class="t-container t-mx-auto t-px-6 t-pb-5">
    <CenteredHero
      title="Our Projects"
      desc="We're improving the open source ecosystem by creating useful, creative, and free software with the world's latest technology."
      icon="/icons/projects.svg"
    />
    <section id="projects" class="t-py-8">
      <h1
        class="t-text-3xl t-screen-tablet-landscape:t-text-4xl t-screen-pc:t-text-5xl t-font-bold t-mb-5"
      >
        Active Projects
      </h1>
      <markdown-content :content="activeProjectsMarkdown" :center="false"/>

      <div class="project-cards-container">
        <project-card
          v-for="(project, id) in activeProjects"
          :key="id"
          :project="project"
        />
      </div>
    </section>
    <section class="t-py-8">
      <h1
        class="t-text-3xl t-screen-tablet-landscape:t-text-4xl t-screen-pc:t-text-5xl t-font-bold t-mb-5"
      >
        Standby Projects
      </h1>
      <div class="project-cards-container">
        <project-card
          v-for="(project, id) in standbyProjects"
          :key="id"
          :project="project"
        />
      </div>
    </section>
    <section class="t-py-8">
      <h1
        class="t-text-3xl t-screen-tablet-landscape:t-text-4xl t-screen-pc:t-text-5xl t-font-bold t-mb-5"
      >
        External Projects
      </h1>
      <div class="project-cards-container">
        <project-card
          v-for="(project, id) in externalProjects"
          :key="id"
          :project="project"
        />
      </div>
    </section>
    <section class="t-py-8">
      <h1
        class="t-text-3xl t-screen-tablet-landscape:t-text-4xl t-screen-pc:t-text-5xl t-font-bold t-mb-5"
      >
        Project Concepts
      </h1>
      <div class="project-cards-container">
        <project-card
          v-for="(project, id) in conceptProjects"
          :key="id"
          :project="project"
        />
      </div>
    </section>
  </div>
</template>

<script>
import ProjectCard from '@/components/ProjectCard.vue'
export default {
  async asyncData({$content, params, error}) {
    const projectsDataStore = await $content('projects', 'projects').fetch()
    const activeProjectsMarkdown = await $content('projects', 'active').fetch()
    console.log(projectsDataStore)
    const activeProjects = projectsDataStore.active
    const standbyProjects = projectsDataStore.standby
    const externalProjects = projectsDataStore.external
    const conceptProjects = projectsDataStore.concept
    return {
      activeProjects,
      standbyProjects,
      externalProjects,
      conceptProjects,
      activeProjectsMarkdown,
    }
  },
  components: {
    ProjectCard,
  },
}
</script>

<style>
.project-cards-container {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
}

/*
.g-section-heading {
  margin: 0 auto;
  margin-bottom: 4rem;
} */

@media screen and (max-width: 768px) {
  .g-section-heading {
    text-align: center;
  }
}
</style>
