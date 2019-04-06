<template>
  <div class="blog-template">
    <header class="header">
      <strong>
        <g-link to="/" class="nav__link">{{ $static.metaData.siteName }}</g-link>
      </strong>
      <NavBar/>
    </header>
    <slot/>
  </div>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>
<script>
import NavBar from "../components/NavBar";

export default {
  components: {
    NavBar
  }
};
</script>


<style>
.blog-template > :not(.header) {
  max-width: 1200px;
  width:100%;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}

.nav__link {
  margin-left: 20px;
}
.blog-template img{
  display:block;
  max-width:500px;
  width:auto;
  
}
.blog-template ol{
  padding:1rem 2rem;
}
.blog-template code {
  padding:2rem;
  background:#333;
  color:#eee;
  display:block;
  overflowY: scroll;
}
</style>
