<template>
  <div class="t-container t-mx-auto t-px-6 t-pb-5">
    <!-- Hero -->
    <section class="t-grid t-place-items-center t-h-screen">
      <div class="t-screen-tablet-landscape:t-flex t-justify-between">
        <div class="w-full t-screen-tablet-landscape:t-w-2/5 flex flex-col">
          <h1
            class="t-text-3xl t-screen-tablet-landscape:t-text-4xl t-screen-pc:t-text-5xl t-font-bold"
          >
            Learn by Building <br />
            Open Source Software
          </h1>
          <p class="t-text-xl t-mt-4">
            We're on a mission to empower people to create open-source software
            for their communities and societies!
          </p>
          <div class="flex t-items-center t-mt-4">
            <nuxt-link to="/projects">
              <v-btn
                elevation="4"
                outlined
                color="primary"
                class="t-mr-4 t-font-bold t-bg-green-400"
                large
                ><v-icon class="t-mr-2">mdi-lightbulb</v-icon>Projects</v-btn
              >
            </nuxt-link>
            <v-btn
              href="http://meet.grey.software"
              elevation="4"
              color="primary"
              large
              class="t-font-bold"
              ><v-icon class="t-mr-2">mdi-calendar-plus</v-icon>Get
              Mentorship</v-btn
            >
          </div>
        </div>
        <div
          class="t-screen-phone:t-w-4/5 t-screen-tablet-landscape:t-w-1/2 t-pl-5 t-mt-5"
        >
          <img
            class="t-screen-phone:t-mx-auto t-screen-tablet-landscape:t-float-right"
            src="@/assets/img/open-source.svg"
          />
        </div>
      </div>
    </section>
    <section class="t-pb-12">
      <content-cols-1x2 title="What we do" :cols="whatWeDo" />
    </section>
    <!-- Help us stay alive -->
    <!-- Who are we? -->
    <!-- <section class="py-12">
      <h1 class="text-5xl font-bold mb-4">
        Volunteer with us! Were looking for
      </h1>
      <div class="flex pt-5 justify-space-between items-center">
        <div
          v-for="role in roles"
          :key="role.label"
          class="flex-col align-center w-1/5"
        >
          <img class="icon-who-we-are" :src="role.icon" />
          <h4 class="text-xl mt-4">{{ role.label }}</h4>
        </div>
      </div>
      <h1 class="text-2xl font-bold mt-8">
        to join us as we build a beautiful, open source future!
      </h1>
      <div class="flex mt-5">
        <nuxt-link to="/projects">
          <v-btn elevation="4" x-large color="primary" class="mr-4"
            ><v-icon>mdi-discord</v-icon>Join the Community</v-btn
          >
        </nuxt-link>
        <v-btn
          link
          to="http://meet.grey.software"
          elevation="4"
          x-large
          outlined
          color="primary"
          ><v-icon>mdi-message-video</v-icon>Volunteer Onboarding</v-btn
        >
      </div>
    </section> -->
    <section class="t-pb-10">
      <h1
        class="t-text-2xl t-screen-tablet-landscape:t-text-3xl t-screen-pc:t-text-5xl t-font-bold"
      >
        Check out what we're building!
      </h1>
      <div class="flex flex-wrap">
        <project-card
          v-for="(project, id) in projects"
          :key="id"
          :project="project"
        />
      </div>
    </section>

    <!-- <section class="container mt-5 pb-5 pl-4">
      <h1 class="text-4xl font-bold">What we offer</h1>
      <div class="row mt-5">
        <div class="col-md" style="height: 434px">
          <img class="three-col-icon" src="@/assets/icons/explorer.svg" />
          <h1 class="three-col-heading mt-5" style="height: 88px">Explorer</h1>
          <p class="three-col-body mt-2">
            Bring your creative app ideas to life with less chaos and more
            clarity with the Grey Software Explorer service!
          </p>
          <div class="mt-4">
            <b-button
              size="sm"
              variant="outline-primary"
              class="mr-4 g-btn-alt flex items-center"
              target="_blank"
            >
              Enrollment Full
            </b-button>
          </div>
        </div>
        <div class="col-md" style="height: 434px">
          <img class="three-col-icon" src="@/assets/icons/apprentice.svg" />
          <h1 class="three-col-heading mt-5" style="height: 88px">
            Apprentice
          </h1>
          <p class="three-col-body mt-2">
            Contribute to established open source software with guidance and
            structure from a Grey Software mentor!
          </p>
          <div class="mt-4">
            <nuxt-link to="/apprentice">
              <b-button
                size="sm"
                class="mr-4 g-btn flex items-center"
                target="_blank"
              >
                Check it out!
              </b-button>
            </nuxt-link>
          </div>
        </div>
        <div class="col-md" style="height: 434px">
          <img class="three-col-icon" src="@/assets/icons/web-portfolio.svg" />
          <h1 class="three-col-heading mt-5" style="height: 88px">
            Web Portfolio
          </h1>
          <p class="three-col-body mt-2">
            Learn the technologies that power the web with an instructor as you
            build a portfoilio of web components!
          </p>
          <div class="mt-4">
            <b-button
              size="sm"
              variant="outline-primary"
              class="mr-4 g-btn-alt flex items-center"
              target="_blank"
            >
              Enrollment Full
            </b-button>
          </div>
        </div>
      </div>
    </section> -->

    <!-- <section class="container mt-5 pl-4 pb-5">
      <h1 class="text-4xl font-bold">
        What do our
        <br />students have <br />to say?
      </h1>
      <div class="row mt-5">
        <div class="col" style="padding-left: 20px">
          <h1 style="max-width: 84%" class="g-text-testimonial mt-5">
            “I have been programming on the side for the past year now, mainly
            using online resources to pair program... yet one session with my
            mentor was more enriching than hours spent on these side tutorials.”
          </h1>
          <p class="g-section-body mt-4">
            Osama -
            <span class="font-italic">Grey Software Explorer</span>
          </p>
        </div>
      </div>
      <div class="row mt-5">
        <div class="col" style="padding-right: 20px; text-align: right">
          <h1 class="g-text-testimonial mt-5">
            “I got to experience what it was like being onboarded into a
            codebase and collaborating with a skilled developer and designer. I
            got the software development education I was looking for."
          </h1>
          <p class="g-section-body mt-4" style="max-width: 100%">
            Milind -
            <span class="font-italic">Grey Software Apprentice</span>
          </p>
        </div>
      </div>
      <div class="row mt-5">
        <div class="col" style="padding-left: 20px">
          <h1 style="max-width: 84%" class="g-text-testimonial mt-5">
            “I built a collection of real web components that I would see when
            browsing the web. I was empowered to be a web developer and start
            creating my own websites.”
          </h1>
          <p class="g-section-body mt-4">
            Nina -
            <span class="font-italic">Web Portfolio Program</span>
          </p>
        </div>
      </div>
      <p class="g-text-testimonial mt-5">
        See more success stories
        <nuxt-link
          to="/success-stories"
          style="color: var(--color-gold)"
          class="font-italic"
          >here!</nuxt-link
        >
      </p>
    </section> -->
  </div>
</template>

<script>
import Contributor from '@/components/Contributor'
import ContentCols1x2 from '@/components/ContentCols1x2'

export default {
  components: {
    Contributor,
    ContentCols1x2,
  },
  async asyncData({$content, params, error}) {
    const projectsDataStore = await $content('projects', 'projects').fetch()
    const projects = projectsDataStore.active
    const contributorsDataStore = await $content('contributors').fetch()

    const contributors = Object.keys(contributorsDataStore.contributors).map(
      (username) => {
        const user = contributorsDataStore.contributors[username]
        return {
          username: user.username,
          avatar: user.avatar,
          link: user.link,
        }
      },
    )
    return {projects, contributors}
  },
  data() {
    return {
      whatWeDo: [
        {
          title: 'Create',
          desc:
            'We create free apps and tools to improve the open source software ecosystem!',
          icon: '/icons/create.svg',
          link: {
            label: 'Our projects',
            internal: '/projects',
            href: '',
          },
        },
        {
          title: 'Educate',
          desc:
            'We research software development education strategies!',
          icon: '/icons/educate.svg',
          link: {
            label: 'Learn More',
            internal: '/educate',
            href: '',
          },
        },
      ],

      roles: [
        {
          label: 'Engineers',
          icon: '/icons/engineers.svg',
        },
        {
          label: 'Designers',
          icon: '/icons/designers.svg',
        },
        {
          label: 'Educators',
          icon: '/icons/educators.svg',
        },
        {
          label: 'Creatives',
          icon: '/icons/creatives.svg',
        },
        {
          label: 'Strategists',
          icon: '/icons/strategists.svg',
        },
      ],
    }
  },
}
</script>