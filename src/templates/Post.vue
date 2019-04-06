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
  padding: 6rem 1rem;
  max-width: 1000px;
  margin: 0 auto;
}
.blog--post > * {
  font-family: var(--main-font);
  line-height: 1.5;
  text-align: justify;
}
.blog--post h1,h2,h3,h4,h5,h6{
  font-family: var(--second-font);
  margin: 2rem 0;
  text-align:center
}
h1 {
  text-align: center;
  font-size: 3rem;
  color: #333;
  font-family: var(--second-font);
  margin-bottom: 2rem;
}
ul {
  padding: 1rem 2rem;
}
</style>