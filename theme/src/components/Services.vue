<template>
  <section
    id="services"
    class="overflow-hidden"
  >
    <v-row
      class="accent"
      no-gutters
    >
      <v-col
        class="hidden-sm-and-down"
        md="6"
      >
        <v-img
          :src="require('@/assets/services.jpg')"
          height="100%"
          max-width="100%"
        />
      </v-col>

      <v-col
        class="text-center pa-5"
        cols="12"
        md="6"
      >
        <v-row
          class="fill-height"
          align="center"
          justify="center"
        >
          <v-col cols="12">
            <base-bubble-2
              style="transform: translateX(55%)"
            />
            <base-heading class="info--text">
              Achievement
            </base-heading>

            <base-text class="mb-5">
              I was graduated with an award as Honor Graduates for my outstanding achievement in Hacktiv8 Bootcamps Training program with Final Grade 92%.<br>
              Here a credentials for my achievements.<br>
              <a
                href="https://hire.hacktiv8.com/verify/fsjs/YodiFebrian-20200709"
                style="color: red"
              >
                Click Here
              </a>
            </base-text>

            <base-heading class="info--text">
              Services
            </base-heading>

            <base-text class="mb-5">
              I provide several service for Development state of web-app.
            </base-text>
          </v-col>

          <v-col
            v-for="(service, i) in services"
            :key="i"
            class="text-center mb-3"
            md="6"
          >
            <v-avatar
              class="elevation-6 mb-2"
              color="#69A1BB"
              size="64"
              tile
            >
              <v-icon
                dark
                size="52"
                v-text="service.icon"
              />
            </v-avatar>

            <base-text>
              <div
                class="mb-2"
                v-text="service.name"
              />
              <div v-html="service.blurb" />
            </base-text>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </section>
</template>

<script>
  export default {
    name: 'Services',

    data: () => ({
      services: [
        {
          name: 'Fullstack Development',
          icon: 'mdi-clipboard-text-outline',
          blurb: 'I providing a service for building full App services with full documentation if needed',
        },
        {
          name: 'Back-end Development',
          icon: 'mdi-pencil-outline',
          blurb: 'I providing a service for building a server app with Node.Js and Python',
        },
        {
          name: 'Front-End Development',
          icon: 'mdi-settings-outline',
          blurb: 'I providing a service for building front-end development app using SPA with Vue, React and React-Native',
        },
        {
          name: 'Debugger and Tester',
          icon: 'mdi-account',
          blurb: 'I providing a service for debugging Api and Client side with Jest.Js and Istanbul Coverage',
        },
      ],
    }),
  }
</script>
