<template>
  <a
    :href="link"
    class="nav__link d-none d-md-flex flex-column ml-6"
    @mouseenter="hover = true"
    @mouseleave="hover = false"
  >
    <v-icon class="nav__link-icon" :color="hover ? 'blue' : 'black'" small>
      {{ icon }}
    </v-icon>
    <p class="nav__link-text mb-0 text-center">{{ title.toUpperCase() }}</p>
  </a>
</template>

<script>
export default {
  name: 'NavLink',
  props: {
    link: {
      type: String,
      default: '/',
    },
    icon: {
      type: String,
      default: 'mdi-heart',
    },
    title: {
      type: String,
      default: 'Link',
    },
  },

  data() {
    return {
      hover: false,
    }
  },
}
</script>
