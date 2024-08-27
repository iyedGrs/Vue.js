<template>
  <div>
    <nav
      :class="[`bg-${theme}`, `navbar-${theme}`, 'navbar', 'navbar-expand-lg']"
    >
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li v-for="(page, index) in pages" class="nav-item" :key="index">
          <a
            class="nav-link"
            :class="{ active: activePage == index }"
            aria-current="page"
            :href="page.link.url"
            @click.prevent="navLinkClick(index)"
            >{{ page.link.text }}
          </a>
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
export default {
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
