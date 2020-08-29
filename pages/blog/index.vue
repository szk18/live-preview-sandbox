<template>
  <div>
    <h1>記事一覧</h1>
    <ul>
      <li v-for="item in articles" :key="item.id">
        <nuxt-link :to="`/blog/${item.id}`">{{ item.title }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios, $config }) {
    const { data } = await $axios.get(
      `https://suzuki-blog.microcms.io/api/v1/blog/`,
      {
        headers: {
          "X-API-KEY": $config.apiKey
        }
      }
    );
    return { articles: data.contents };
  }
  // methods: {
  //   formatDate(date) {
  //     const options = { year: "numeric", month: "long", day: "numeric" };
  //     return new Date(date).toLocaleDateString("ja", options);
  //   }
  // }
};
</script>
