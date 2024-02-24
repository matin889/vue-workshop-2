<template>
  <div class="container">
    <header>
      <slot name="header"></slot>
    </header>
    <main>
      <slot name="main"></slot>
    </main>
    <footer>
      <slot name="footer"></slot>
    </footer>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'BaseLayout'
})
</script>

<style scoped>
.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
}

header,
footer {
  background-color: #333;
  color: white;
  padding: 10px;
  text-align: center;
}
footer {
  border-top: 1px solid #ccc;
  font-size: 0.8em;
  margin-top: 20px;
}
</style>
