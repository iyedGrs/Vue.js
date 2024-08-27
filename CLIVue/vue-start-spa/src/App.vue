<template>
  <div>
    <NavBar
      :active-page="activePage"
      :pages="pages"
      :nav-link-click="(index) => (activePage = index)"
    ></NavBar>
    <PageViewer v-if="pages.length > 0" :page="pages[activePage]" />
  </div>
</template>

<script>
import PageViewer from "./components/PageViewer.vue";
import NavBar from "./components/NavBar.vue";
export default {
  components: {
    PageViewer,
    NavBar,
  },
  created() {
    this.fetchData();
  },
  data() {
    return {
      activePage: 0,
      pages: [],
    };
  },
  methods: {
    async fetchData() {
      const res = await fetch("pages.json");
      const data = await res.json();
      this.pages = data;
    },
  },
};
</script>
