<template>
  <v-app>
    <!-- Nav -->
    <v-app-bar
      id="nav"
      class="nav blue--background px-md-6 elevation-5 mb-10"
      :clipped-left="clipped"
    >
      <v-btn class="d-md-none" icon @click.stop="drawer = !drawer">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
      <a href="/">
        <v-img
          :src="require(`~/assets/images/logo-tcs.jpg`)"
          max-height="3.5rem"
          max-width="6rem"
          contain
        ></v-img>
      </a>

      <VSpacer />

      <NavLink
        v-for="item in links"
        :key="item.link"
        :link="item.link"
        :title="item.title"
        :icon="item.icon"
      />

      <v-btn class="d-md-none" text>INICIA SESIÓN</v-btn>

      <v-btn class="ml-6" color="primary" outlined text>
        REGISTRATE <v-icon class="mx-0" right>mdi-menu-down</v-icon>
      </v-btn>

      <v-btn class="d-none d-md-block ml-6" color="primary">
        PUBLICA TU OFERTA
      </v-btn>
    </v-app-bar>

    <!-- Main -->
    <v-main>
      <v-container class="px-10 mb-16">
        <nuxt />
      </v-container>
    </v-main>

    <!-- Subscribe form -->
    <v-row class="subscribe">
      <v-col class="subscribe__title col-12 col-md-6">
        <h2 class="text-center">Suscríbete para seguir informado (a)</h2>
      </v-col>
      <v-col class="col-12 col-md-6">
        <v-form>
          <v-row class="justify-center">
            <v-col class="col-12 col-md-8 pb-0">
              <v-text-field
                v-model="name"
                solo
                color="blue"
                class="subscribe__input text-center elevation-0"
                :rules="[rules.required, rules.email]"
                label="Ingresa tu mail"
                placeholder="Ingresa tu mail"
                required
              ></v-text-field>
            </v-col>

            <v-col class="col-12 col-md d-flex justify-center justify-md-start">
              <v-btn
                depressed
                large
                class="subscribe__submit blue--text white px-10"
              >
                ENVIAR
              </v-btn>
            </v-col>
          </v-row>
        </v-form>
      </v-col>
    </v-row>

    <footer class="footer">
      <!-- Sitemap -->
      <v-row class="footer__sitemap">
        <!-- Logo -->
        <v-col class="footer__col col-12 col-md-2">
          <v-img
            :src="require(`~/assets/images/logo-white-tcs.png`)"
            max-width="15rem"
          ></v-img>
        </v-col>

        <!-- Nosotros -->
        <v-col class="footer__col col-12 col-md-3">
          <h3 class="footer__title">Nosotros</h3>
          <a href="/" class="footer__link">Sobre nosotros</a>
          <a href="/" class="footer__link">¿Necesitas contactarnos?</a>
          <a href="/" class="footer__link">
            Privacidad y protección de datos personales
          </a>
          <a href="/" class="footer__link"
            >Política de moderación de publicaciones</a
          >
        </v-col>

        <!-- Web -->
        <v-col class="footer__col col-12 col-md-2">
          <h3 class="footer__title">Web</h3>
          <a href="/" class="footer__link">Regístrate</a>
          <a href="/" class="footer__link">Iniciar sesión</a>
          <a href="/" class="footer__link">Ofertas de trabajo</a>
          <a href="/" class="footer__link">Publica tu oferta</a>
          <a href="/" class="footer__link">Servicios</a>
          <a href="/" class="footer__link">Comunidad</a>
        </v-col>

        <!-- Logos -->
        <v-col class="footer__col col-12 col-md-5">
          <h3>Somos parte de:</h3>
          <v-row class="justify-center align-end">
            <v-col cols="3">
              <v-img
                class="d-inline-block"
                :src="require(`~/assets/images/logo-empresa-b.png`)"
              ></v-img>
            </v-col>
            <v-col cols="3">
              <v-img
                class="d-inline-block"
                :src="require(`~/assets/images/logo-corfo.png`)"
              ></v-img>
            </v-col>
            <v-col cols="3">
              <v-img
                class="d-inline-block"
                :src="require(`~/assets/images/logo-prochile.png`)"
              ></v-img>
            </v-col>
            <v-col cols="3">
              <v-img
                class="d-inline-block"
                :src="require(`~/assets/images/logo-chileglobal-ventures.png`)"
              ></v-img>
            </v-col>
            <v-col cols="6">
              <v-img
                class="d-inline-block"
                :src="require(`~/assets/images/logo-chilecompra.png`)"
              ></v-img>
            </v-col>
          </v-row>
        </v-col>
      </v-row>

      <!-- Social -->
      <v-row dark class="footer__social justify-center justify-md-between">
        <v-col class="footer__social-text text-center col-12 col-md-4">
          <p>Únete a la conversación en:</p>
          <v-icon color="white">mdi-facebook</v-icon>
          <v-icon color="white">mdi-linkedin</v-icon>
          <v-icon color="white">mdi-instagram</v-icon>
          <v-icon color="white">mdi-twitter</v-icon>
          <v-icon color="white">mdi-youtube</v-icon>
        </v-col>
        <v-col
          class="footer__social-text text-center col-12 col-md-4 offset-md-4"
        >
          <p>&copy; {{ new Date().getFullYear() }}. Felipe Castro Richter</p>
        </v-col>
      </v-row>
    </footer>
  </v-app>
</template>

<script>
import NavLink from '~/components/NavLink.vue'

export default {
  components: { NavLink },

  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'TRABAJO CON SENTIDO',
      links: [
        {
          link: '/ofertas',
          title: 'ofertas',
          icon: 'mdi-briefcase',
        },
        {
          link: '/servicios',
          title: 'servicios',
          icon: 'mdi-handshake',
        },
        {
          link: '/comunidad',
          title: 'comunidad',
          icon: 'mdi-wechat',
        },
        {
          link: '/organizaciones',
          title: 'ORGANIZACIONES',
          icon: 'mdi-account-supervisor',
        },
        {
          link: '/login',
          title: 'inicia sesión',
          icon: 'mdi-account-circle',
        },
      ],
      rules: {
        required: (val) => !!val || 'Valor requerido.',
        email: (value) => {
          const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
          return pattern.test(value) || 'Mail inválido.'
        },
      },
    }
  },
}
</script>
