<template>
  <BlogLayout>
    <div v-html="$page.post.content" class="blog--post"></div>
  </BlogLayout>
</template>

<page-query>
query Post ($path: String!){
  post: post(path: $path){
    title
    path
    content
  }
}

</page-query>

<script>
export default {
  metaInfo() {
    return {
      title: this.$page.post.title
    };
  }
};
</script>

<style >
.blog--post {
  padding-top: 6rem;
  max-width: 1000px;
  margin: 0 auto;
}

h1 {
  text-align: center;
  font-size: 3rem;
  color: #333;
  font-family: var(--second-font);
  margin-bottom: 2rem;
}
h2 {
  margin: 1rem 0;
}
p {
  font-family: var(--main-font);
  line-height: 1.5;
  text-align: justify;
}
ul {
  padding: 1rem 2rem;
}
</style>


// query{
//   post(path:"/blog/second-blog-post"){
//     title
//     path
//     content
//   }
// }