<template>
  <div id="app">
    <BaseLayout>
      <template v-slot:header>
        <h1>Movie Cards</h1>
      </template>

      <template v-slot:main>
        <div class="cards">
          <MovieCard v-for="movie in movies" :movie="movie" :key="movie.title">
            <template v-slot:button="{ movie }">
              <button @click="handleCardClick(movie)">Watch {{ movie.title }}</button>
            </template>
          </MovieCard>
        </div>
      </template>

      <template v-slot:footer>
        <p>Copyrights@2023</p>
      </template>
    </BaseLayout>
  </div>
</template>

<script>
import MovieCard from '@/components/MovieCard.vue'
import BaseLayout from '@/components/BaseLayout.vue'

import { defineComponent } from 'vue'

export default defineComponent({
  name: 'App',
  components: {
    MovieCard,
    BaseLayout
  },
  // emits: ['card-clicked'],
  data() {
    return {
      movies: [
        { title: 'Tare Jameen', director: 'Aamir', year: 2010 },
        { title: 'Ishq', director: 'Salman', year: 2012 },
        { title: 'World', director: 'Stephen', year: 2000 }
      ]
    }
  },
  methods: {
    handleCardClick(movie) {
      console.log(`Clicked on ${movie.title} directed by ${movie.director}`)
    }
  }
})
</script>

<style>
#app {
  text-align: center;
  margin-top: 20px;
}
.cards {
  display: flex;
  justify-content: center;
}
</style>
