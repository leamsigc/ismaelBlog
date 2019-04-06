<template>
  <div>
    <div class="layout">
      <header class="header">
        <strong>
          <g-link to="/" class="nav__link">{{ $static.metaData.siteName }}</g-link>
        </strong>
        <NavBar/>
      </header>
    </div>
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
@import url("https://fonts.googleapis.com/css?family=Lora:400,700|Merriweather:300,400");
:root {
  --main-color: #6562e8;
  --main-font: "Merriweather", serif;
  --second-font: "Lora", serif;
}
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
body {
  /* font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif; */
  margin: 0;
  padding: 0;
  line-height: 1.5;
  font-family: "Merriweather", serif;
}
h1,
h2,
h3,
h4 {
  font-family: "Lora", serif;
}
.layout > :not(.header) {
  max-width: 1200px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}

.header {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 80px;
  width: 100%;
  color: #333;
  z-index: 1000;
}

.nav__link {
  margin-left: 20px;
}
</style>
