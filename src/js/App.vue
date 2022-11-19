<template>
  <nav>
    <template
      v-for="(routePath, routeName, index) of menuLinks"
      :key="index"
    >
      <preloadable-router-link
        :to="routePath"
      >{{ routeName }}</preloadable-router-link>
      <span class="separator" v-if="index < menuLinksAmount - 1"> | </span>
    </template>
  </nav>

  <main>
    <router-view/>
  </main>

  <footer>
    <p>
      Grab this template at: <a href="https://github.com/Anoesj/vue-vite-gh-pages-template/">https://github.com/Anoesj/vue-vite-gh-pages-template/</a>
    </p>
  </footer>
</template>

<script>
  export default {

    data () {
      return {
        menuLinks: {
          'Home': '/',
          'Contact': '/contact',
          'Non-existent route': '/asdfghjkl',
        },
      };
    },

    computed: {
      menuLinksAmount () {
        return Object.keys(this.menuLinks).length;
      },
    },

  };
</script>

<style>
 * {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
	font-family: 'Montserrat', sans-serif;
}

.app {
	display: flex;
	flex-direction: column;
	align-items: center;
	padding: 2rem;
	height: 100vh;
}
</style>