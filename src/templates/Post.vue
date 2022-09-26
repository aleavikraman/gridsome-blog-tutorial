<template>
  <Layout>
    <div class="has-text-centered">
      <h1 class="title is-1">
        {{ $page.post.title }}
      </h1>
    </div>

    <div class="post content section container">
      <figure v-if="$page.post.cover_image" class="image is-16by9">
        <g-image :alt="$page.post.alt" :src="$page.post.cover_image" />
      </figure>

      <div v-html="$page.post.content" />
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo() {
    return {
      title: this.$page.post.title,
      meta: [
        {
          name: 'description',
          content: this.$page.post.description,
        },
      ],
    };
  },
};
</script>

<page-query>
query Post($id: ID!) {
  post: post(id: $id) {
    title
    path
    description
    content
    alt
    cover_image(width: 860, blur: 10)
  }
}
</page-query>
