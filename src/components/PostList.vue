<template>
  <div class="card">
    <!-- if there is an image show it. If user clicks image take to url path -->
    <g-link v-if="post.cover_image" class="card-image" :to="post.path">
      <figure class="image is-16by9">
        <g-image :alt="post.alt" :src="post.cover_image" fit="contain" />
      </figure>
    </g-link>
    <div class="card-content  has-text-centered">
      <!-- click the title link to go to blog post -->
      <g-link :to="post.path" class=" has-text-weight-bold is-size-3">
        {{ post.title }}
      </g-link>
      <!-- show description section of blog -->
      <div class="content" v-html="post.description" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      default() {
        return {};
      },
    },
  },
};
</script>
<style lang="scss">
.card {
  width: 500px;
  height: max-content;
  margin-top: 30px;
}
</style>
