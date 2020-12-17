<template>
  <div>
    <div class="relative w-full h-full max-w-4xl m-auto">
      <!-- Background Cards -->
      <div
        class="absolute inset-0 z-0 origin-center transform bg-green-400 opacity-75 md:block shadow-2xl rounded"
        style="--transform-rotate: -4deg"
      ></div>
      <div
        class="absolute inset-0 z-0 origin-center transform bg-purple-400 opacity-50 md:block shadow-2xl rounded"
        style="--transform-rotate: 3deg"
      ></div>
      <!-- Profile Card -->
      <div
        class="relative flex flex-col z-20 w-full min-h-full sm:h-full bg-white shadow-2xl rounded"
      >
        <!-- Header -->
        <profile-header></profile-header>
        <!-- Body -->
        <div class="flex-1 py-4 sm:overflow-hidden">
          <div class="h-full px-4 overflow-auto lg:px-12">
            <div class="prose max-w-none">
              <h2>Welcome!</h2>
              <p>
                My name is Jen Dooley. I'm a Frontend Engineer and
                Entrepreneur from Boulder, CO and I have a Computer
                Science engineering degree (B.S.) University of
                Colorado Boulder.
              </p>
              <h2>Languages and Frameworks</h2>
              <p>
                I specialize in the Vue.js ecosystem but I have
                experience with other frameworks such as Laravel and
                React.js as well. I have worked with many of the most
                competative CSS design frameworks such as Bootstrap 4,
                TailwindCSS and Vuetify.
              </p>
              <skill
                v-for="skill in skillz"
                :key="skill.title"
                :skill="skill"
                class="max-w-2xl"
              ></skill>
              <p>
                I am always working towards improving my skills and
                learning new things; I recently learned React and
                TailwindCSS.
              </p>
              <h2>Portfolio</h2>
              <p>
                In 2017, I started
                <a
                  href="https://illuminationfoundry.com/"
                  target="_blank"
                  rel="noopener"
                  class="text-lg font-semibold focus:outline-none focus:bg-green-200 hover:bg-green-200 rounded p-1"
                  >Illumination Foundry</a
                >
                with a couple of partners to provide professional
                web-application services to small businesses, clubs,
                and non-profits. Since then we have worked with
                companies to create marketing websites, analytic
                dashboards, and full CRMs.
              </p>
            </div>
            <div class="max-w-none">
              <project-card
                v-for="project in projects"
                :key="project.title"
                :project="project"
              ></project-card>
            </div>
            <div class="prose max-w-none mt-12 mb-24">
              <h2>More About Me</h2>
              <p>
                I love spending time outside. Over the years I've
                enjoyed outdoor hobbies, such as hiking, camping,
                snowboarding, horseback riding, paintball, disk golf,
                and beer league kickball. 😊
              </p>
              <p>
                If you'd like to work together or have any questions,
                please feel free to shoot me an email!
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ProfileHeader from '../components/Header';
import ProjectCard from '../components/ProjectCard';
import Skill from '../components/Skill';

export default {
  components: {
    ProfileHeader,
    ProjectCard,
    Skill,
  },
  data() {
    return {
      skillz: [
        {
          title: 'HTML',
          proficiency: 90,
          color: 'purple',
        },
        {
          title: 'CSS',
          proficiency: 85,
          color: 'purple',
        },
        {
          title: 'Javascript',
          proficiency: 80,
          color: 'purple',
        },
        {
          title: 'Vue',
          proficiency: 90,
          color: 'purple',
        },
        {
          title: 'React',
          proficiency: 75,
          color: 'purple',
        },
        {
          title: 'Laravel',
          proficiency: 70,
          color: 'purple',
        },
        {
          title: 'UI Design',
          proficiency: 55,
          color: 'purple',
        },
      ],
      projects: [
        {
          title: 'Colorado Wedding Productions',
          description:
            'A fullstack web application and integrated marketing website for a local wedding production company. The application covers client management, paperwork completion, and invoicing. Built using Laravel.',
          link: 'https://coloradoweddingproductions.com/',
          imageUrl: 'cwp.png',
          imageAlt: 'Colorado Wedding Productions',
          color: 'green',
        },
        {
          title: 'Strabo Partners',
          description:
            'A marketing website for a local consulting company. Built using Nuxt.js.',
          link: 'https://strabo.partners/',
          imageUrl: 'strabo.png',
          imageAlt: 'Strabo Partners',
          color: 'purple',
        },
        {
          title: 'TrainingBeta Programs',
          description:
            'A web application for a rock climbing couching company. The applications is used for their clients to view and track their progress on programs. Built using Vue.js & Laravel',
          link: 'https://programs.trainingbeta.com',
          imageUrl: 'training-beta.png',
          imageAlt: 'TrainingBeta Application',
        },
      ],
    };
  },
};
</script>
