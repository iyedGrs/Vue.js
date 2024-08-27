<template>
  <div>
    <nav
      :class="[`bg-${theme}`, `navbar-${theme}`, 'navbar', 'navbar-expand-lg']"
    >
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li v-for="(page, index) in pages" class="nav-item" :key="index">
          <NavBarLink
            :page="page"
            :is-active="index == activePage"
            @click.prevent="navLinkClick(index)"
          >
          </NavBarLink>
        </li>
      </ul>
      <form class="d-flex">
        <button class="btn btn-primary" @click.prevent="changeTheme()">
          Toggle NavBar
        </button>
      </form>
    </nav>
  </div>
</template>
<script>
import NavBarLink from "./NavBarLink.vue";
export default {
  components: {
    NavBarLink,
  },
  props: ["pages", "activePage", "navLinkClick"],

  data() {
    return {
      theme: "light",
    };
  },
  methods: {
    changeTheme() {
      let theme = "light";
      if (this.theme == "light") {
        theme = "dark";
      }
      this.theme = theme;
    },
  },
};
</script>
