<template>
  <ScholarNav />
  <Main />
  <Footer />
</template>

<script>
import ScholarNav from "../components/scholarNav.vue";
import Main from "../components/main.vue";

import Footer from "../components/footer.vue";
export default {
  components: {
    ScholarNav,
    Main,
    Footer,
  },
  data() {
    return {};
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
