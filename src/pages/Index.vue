<template>
  <Layout>
    <header class="header">
      <h1 class="title size-1 has-text-centered pt-5">Gridsome Blog Tutorial</h1>
    </header>
    <main>
      <div class="container">
        <!-- loop through blog card component to show blogs -->
        <PostList v-for="edge in $page.posts.edges" :key="edge.node.id" :post="edge.node" />
      </div>
    </main>
  </Layout>
</template>

<page-query>
  query {
    posts: allPost(filter: { published: { eq: true } }) {
      edges {
        node {
          id
          title
          description
          alt
          cover_image( blur: 10)
          path
        }
      }
    }
  }
  </page-query>

<script>
import PostList from '~/components/PostList.vue';
export default {
  components: {
    PostList,
  },
  metaInfo: {
    title: 'Gridsome Blog Tutorial',
  },
};
</script>

<style>
.container {
  display: grid;
  justify-content: center;
}

main {
  margin: 4% 0;
}
</style>
