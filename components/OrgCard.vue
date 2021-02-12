<template>
  <v-card class="mx-auto">
    <v-img
      class="blue--background lighten-4"
      :src="require(`assets/images/${img}`)"
      :alt="name"
      height="200px"
    ></v-img>

    <v-card-title>
      <v-avatar class="mr-4">
        <img :src="avatar" alt="John" />
      </v-avatar>

      {{ name }}
    </v-card-title>

    <v-card-text class="text-body-1 text-left py-12">{{ text }}</v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: 'Nombre',
    },
    text: {
      type: String,
      default: 'Propósito',
    },
    img: {
      type: String,
      default: 'org-default.png',
    },
    avatar: {
      type: String,
      default: 'https://cdn.vuetifyjs.com/images/john.jpg',
    },
  },
}
</script>

<style lang="scss" scoped></style>
