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
.blog-template > :not(.header),
.blog-template > :not(.hero) {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}

.nav__link {
  margin-left: 20px;
}
</style>
