<template>
  <article>
    <h1>{{ article.title }}</h1>
    <p>{{ article.content }}</p>
    <hr />
    <p>createdAt: {{ formatDate(article.createdAt) }}</p>
  </article>
</template>

<script>
export default {
  async asyncData({ $axios, $config, params }) {
    const { data } = await $axios.get(
      `https://suzuki-blog.microcms.io/api/v1/blog/${params.id}`,
      {
        headers: {
          "X-API-KEY": $config.apiKey
        }
      }
    );
    return { article: data };
  },
  methods: {
    formatDate(date) {
      const options = { year: "numeric", month: "long", day: "numeric" };
      return new Date(date).toLocaleDateString("ja", options);
    }
  }
};
</script>
