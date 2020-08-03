<template>
  <section
    id="about"
    class="overflow-hidden"
  >
    <v-row
      class="white"
      no-gutters
    >
      <v-col
        class="pa-5"
        cols="12"
        md="6"
      >
        <base-bubble-1 style="transform: translate(5%, -5%)" />

        <base-heading class="info--text">
          About Me
        </base-heading>

        <base-text class="mb-5">
          I was graduated from Geological Engineering.<br>
          I have a great passion on IT industries and taking free online course with self learning methods in these last 2 years.<br>
          And then i took 4 months Bootcamps Training on Full Stack JavaScript Developer at Hacktiv8 Indonesia.
        </base-text>

        <base-subheading class="info--text">
          Skills
        </base-subheading>

        <base-text class="mb-5">
          I have extensive experience on JavaScript Language, and medium experience on Python Language.
          Here some of my skills:
        </base-text>

        <v-alert
          outlined
          color="info"
        >
          <v-row
            v-for="(skill, i) in skills"
            :key="i"
            style="color: #69A1BB;"
          >
            <v-col
              class="text-uppercase"
              cols="6"
              v-text="skill.name"
            />

            <v-col
              class="text-right"
              cols="6"
              v-text="`${skill.value}%`"
            />

            <v-progress-linear
              :value="skill.value"
              color="info"
              height="8"
            />
          </v-row>
        </v-alert>
      </v-col>

      <v-col
        class="hidden-sm-and-down"
        md="6"
      >
        <v-img
          :src="require('@/assets/aboutme.png')"
          height="100%"
        />
      </v-col>
    </v-row>
  </section>
</template>

<script>
  export default {
    data: () => ({
      skills: [
        {
          name: 'Node.Js',
          value: 95,
        },
        {
          name: 'Express.Js',
          value: 95,
        },
        {
          name: 'Sequelize',
          value: 95,
        },
        {
          name: 'Json Web Token',
          value: 95,
        },
        {
          name: 'Bcrypt.JS',
          value: 95,
        },
        {
          name: 'MongoDB',
          value: 85,
        },
        {
          name: 'Monolothic',
          value: 95,
        },
        {
          name: 'MicroServices',
          value: 95,
        },
        {
          name: 'Apollo GraphQl',
          value: 85,
        },
        {
          name: 'Redis',
          value: 85,
        },
        {
          name: 'Asyncronous Request',
          value: 90,
        },
        {
          name: 'React with Functional Methods',
          value: 90,
        },
        {
          name: 'Redux',
          value: 90,
        },
        {
          name: 'Thunk',
          value: 85,
        },
        {
          name: 'Material Ui',
          value: 80,
        },
        {
          name: 'Apollo-Client for React',
          value: 85,
        },
        {
          name: 'Vue',
          value: 90,
        },
        {
          name: 'Vuex',
          value: 90,
        },
        {
          name: 'Vuetify',
          value: 90,
        },
        {
          name: 'Python',
          value: 70,
        },
        {
          name: 'Flask',
          value: 70,
        },
      ],
    }),
  }
</script>
