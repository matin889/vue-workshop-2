<template>
  <div class="card">
    <h2>{{ movie.title }}</h2>
    <p>Director: {{ movie.director }}</p>
    <p>Released: {{ movie.year }}</p>
    <slot name="button" :movie="movie">
      <button @click="handleClick">Click Me</button>
    </slot>
  </div>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'MovieCard',
  props: {
    movie: {
      type: Object,
      required: true
    }
  },
  methods: {
    handleClick() {
      this.$emit('card-clicked', this.movie);
    }
  }
});
</script>

<style scoped>
.card {
  background: blue;
  color: white;
  border: 1px solid #ccc;
  padding: 10px;
  margin: 10px;
  max-width: 200px;
}
</style>
