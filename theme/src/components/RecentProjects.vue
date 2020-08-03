<template>
  <section
    id="recent-projects"
    class="overflow-hidden"
  >
    <v-row no-gutters>
      <v-col
        class="primary text-center pa-5 white--text"
        cols="12"
        md="6"
      >
        <base-bubble-1
          style="transform: rotate(180deg) translateX(25%)"
        />

        <base-heading>
          Recent Projects
        </base-heading>

        <base-text class="mb-5">
          Here some project that i did to increase my experience<br>
          For the the rest of my project click on Git Icon.
        </base-text>

        <v-card color="secondary">
          <v-container class="pa-2">
            <v-row>
              <v-col
                v-for="(project, i) in projects"
                :key="i"
                cols="12"
                md="6"
              >
                <a :href=project.url>
                  <v-img
                    :src="require(`@/assets/${project.path}.png`)"
                    max-height="300"
                  />
                </a>
              </v-col>
            </v-row>
          </v-container>
        </v-card>
      </v-col>

      <v-col
        class="hidden-sm-and-down"
        md="6"
      >
        <v-img
          :src="require('@/assets/recentprojects.png')"
          height="100%"
        />
      </v-col>
    </v-row>
  </section>
</template>

<script>
  export default {
    name: 'RecentProjects',

    data: () => ({
      projects: [
        {
          name: 'Hinata Dev-Chat-Bot',
          url: 'https://www.youtube.com/watch?v=r3Ufu5AgCBM',
          path: 'chatbot',
        },
        {
          name: 'E-Commerce',
          url: 'https://blanja-in.web.app/',
          path: 'e-commerce',
        },
        {
          name: 'Guess Picture Game',
          url: 'https://guestimage-a69ed.web.app/',
          path: 'game',
        },
        {
          name: 'Kamvan App',
          url: 'https://kamvan-d2282.firebaseapp.com/',
          path: 'kamvan',
        },
      ],
    }),
  }
</script>
