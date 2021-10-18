<template>
  <dev>
    <h1>何を読もうか？</h1>
    <button @click="getData">
      getData
    </button>
    <ul>
      <li v-for="book in books" :key="book.id">
        <NuxtLink :to="'/books/'+book.id">
          {{ book.title }}
        </NuxtLink>
      </li>
    </ul>
  </dev>
</template>

<script>
export default ({
  data () {
    return {
      books: 'hon'
    }
  },
  methods: {
    async getData () {
      const res = await this.$axios.$get('http://localhost:3100/articles/')
      this.books = res
    }
  }
})
</script>
