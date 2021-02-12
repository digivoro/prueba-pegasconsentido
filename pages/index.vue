<template>
  <v-row class="hero" justify="center">
    <v-col cols="12">
      <v-row justify="center">
        <v-col cols="12" sm="10" md="8" lg="6">
          <h1 class="hero__title mb-10">
            Conoce a las organizaciones que buscan talentos con sentido
          </h1>
        </v-col>
      </v-row>
    </v-col>
    <v-col v-for="org in orgs" :key="org.id" cols="12" sm="6" md="4">
      <org-card :name="org.name" :text="org.text"></org-card>
    </v-col>
  </v-row>
</template>

<script>
import { mapState } from 'vuex'
import OrgCard from '~/components/OrgCard.vue'

export default {
  components: {
    OrgCard,
  },

  data() {
    return {}
  },

  computed: {
    ...mapState(['orgs']),
  },
}
</script>
