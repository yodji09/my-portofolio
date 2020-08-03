<template>
  <div>
  <v-tooltip
    bottom
    v-for="(item, i) in items.slice(0, large ? items.length : 3)"
    :key="i"
  >
    <template v-slot:activator="{ on, attrs }">
      <v-btn
        fab
        class="ma-2"
        color="info"
        :small="!large"
      >
        <a :href="item.link">
        <v-icon
          v-bind="attrs"
          v-on="on"
          dark
          v-text="item.icon"
        />
        </a>
      </v-btn>
    </template>
    <span>{{item.name}}</span>
  </v-tooltip>
  </div>
</template>

<script>
  export default {
    props: {
      large: {
        type: Boolean,
        default: false,
      },
    },

    data: () => ({
      items: [
        {
          name: 'Instagram',
          icon: 'mdi-instagram',
          link: 'https://www.instagram.com/yodi.febrian/',
        },
        {
          name: 'Github',
          icon: 'mdi-git',
          link: 'https://www.github.com/yodji09',
        },
        {
          name: 'Linkedin',
          icon: 'mdi-linkedin',
          link: 'https://www.linkedin.com/in/yodifebrian',
        },
      ],
    }),
  }
</script>
