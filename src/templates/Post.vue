<template>
  <BlogLayout>
    <div v-html="$page.post.content"></div>
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



// query{
//   post(path:"/blog/second-blog-post"){
//     title
//     path
//     content
//   }
// }