<template>
  <v-row>
    <v-col class="text-center">
      <AppSearchInput />
      <blockquote class="blockquote">
        &#8220;First, solve the problem. Then, write the code.&#8221;
        <footer>
          <small>
            <em>&mdash;John Johnson</em>
          </small>
        </footer>
      </blockquote>
      <v-card>
        <v-card-title class="headline"> Cloud Wiki </v-card-title>
        <v-card-text>
          <ul>
            <li v-for="article of articles" :key="article.slug">
              <NuxtLink :to="{ name: 'slug', params: { slug: article.slug } }">
                <img :src="article.img" />
                <div>
                  <h2>{{ article.title }}</h2>
                  <p>{{ article.description }}</p>
                </div>
              </NuxtLink>
            </li>
          </ul>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
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
    const articles = await $content('wiki', params.slug)
      .only(['title', 'description', 'slug'])
      .sortBy('createdAt', 'asc')
      .fetch()

    return {
      articles,
    }
  },
}
</script>
