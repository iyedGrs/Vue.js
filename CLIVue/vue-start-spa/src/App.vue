<template>
  <div>
    <NavBar
      :active-page="activePage"
      :pages="pages"
      :nav-link-click="(index) => (activePage = index)"
    ></NavBar>
    <PageViewer :page="pages[activePage]" />
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
  data() {
    return {
      activePage: 0,
      pages: [
        {
          link: {
            text: "Home",
            url: "index.html",
          },
          pageTitle: "Home",
          content: "This is the home page",
        },
        {
          link: {
            text: "About",
            url: "about.html",
          },
          pageTitle: "About",
          content: "This is the about page",
        },
        {
          link: {
            text: "Contact",
            url: "contact.html",
          },
          pageTitle: "Contact",
          content: "This is the contact page",
        },
      ],
    };
  },
};
</script>
