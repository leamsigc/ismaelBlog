<template>
  <BlogLayout>
    <div class="hero hero-blog">
      <h1 class="title">Resents blogs post</h1>
      <ul>
        <li v-for="post in $page.posts.edges" :key="post.id">
          <g-link :to="post.node.path">{{post.node.title}}</g-link>
        </li>
      </ul>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Error doloremque omnis animi, eligendi magni a voluptatum, vitae, consequuntur rerum illum odit fugit assumenda rem dolores inventore iste reprehenderit maxime! Iusto.</p>
    </div>
  </BlogLayout>
</template>
<page-query>

query Posts{
  posts: allPost{
    edges{
     node{
      path
      title
      id
      
    }
    }
  }
}

</page-query>
<script>
export default {
  metaInfo: {
    title: "Daytona Web developer BLog Posts"
  }
};
</script>
<style>
.hero-blog {
  min-width: 100vw;
  text-align: center;
  align-items: center;
}
</style>
