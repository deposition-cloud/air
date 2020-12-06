<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="12" md="10">
      <div class="text-center">
        <vuetify-logo />
      </div>
      <v-card>
        <v-card-title class="headline"> The Personal Cloud </v-card-title>
        <v-card-text>
          <p>A breath of fresh air</p>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn color="primary" nuxt to="/wiki"> Explore the Wiki </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {}
}
</script>
