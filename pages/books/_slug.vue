<template>
  <div>
    <h1>ここは……一体……</h1>
    今いるのは books/{{ $route.params.slug }} のページです。<br>
    <h3>{{ books.title }}</h3>
    <h4>{{ books.author }}</h4>
    <button @click="getData($route.params.slug)">
      データを取得
    </button><br>
    <NuxtLink to="/">
      どんな本を読んだって良いんだよ。
    </NuxtLink>
  </div>
</template>

<script>
export default ({
  name: 'Button',
  data () {
    return {
      books: 'ここに登録された本が表示されます'
    }
  },
  methods: {
    async getData (id) {
      alert(id)
      const res = await this.$axios.$get('http://localhost:3100/articles/' + id)
      // eslint-disable-next-line no-console
      console.log(res)
      this.books = res
    }
  }
})
</script>
