<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="12" md="10">
      <div class="text-center">
        <vuetify-logo />
      </div>
      <v-card>
        <v-card-title class="headline"> Cloud Wiki </v-card-title>
        <v-card-text>
          <ul>
            <li v-for="article of articles" :key="article.slug">
              <NuxtLink :to="{ name: 'slug', params: { slug: article.slug } }">
                <img :src="article.img" />
                <div>
                  <h2>{{ article.title }}</h2>
                  <p>by {{ article.author.name }}</p>
                  <p>{{ article.description }}</p>
                </div>
              </NuxtLink>
            </li>
          </ul>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn color="primary" nuxt to="/inspire"> Next </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {},
  async asyncData({ $content, params }) {
    const articles = await $content('articles', params.slug)
      .only(['title', 'description', 'img', 'slug', 'author'])
      .sortBy('createdAt', 'asc')
      .fetch()

    return {
      articles,
    }
  },
}
</script>
