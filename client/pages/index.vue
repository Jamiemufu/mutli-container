<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <div class="text-center">
        <logo />
        <vuetify-logo />
      </div>
      <v-card>
        <v-card-title class="headline">
          This page has saved a new homepage via POST
        </v-card-title>
        <v-card-text>
          <v-card-actions>
            <v-spacer />
            <v-btn
              color="primary"
              nuxt
              to="/inspire"
            >
              CHECK HOMEPAGE
            </v-btn>
          </v-card-actions>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo,
  },
  data() {
    return {
      homepage: ''
    }
  },
  created() {
    this.$axios.post('/api/homepages', {
      "Name": "A new homepage",
      "title": "Test API POST homepage",
      "metaData": "Some meta data"
    })
  }
}
</script>
