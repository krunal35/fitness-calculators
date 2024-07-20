<template>
  <div>
    <!-- Main navigation and footer are displayed only if the current route is not a special page -->
        <router-view></router-view>
    <!-- For special pages, only the main content is displayed without the main navigation and footer -->
    <router-view v-if="isSpecialPage" />
  </div>
</template>

<script>

export default {
  name: "App",
  components: {
  },
  computed: {
    isSpecialPage() {
      const { path } = this.$route;
      return (
        path === "/authentication" ||
        path === "/forgotPassword" ||
        path.startsWith("/resetPassword") ||
        path === "/404"
      );
    },
  },
};
</script>

<style></style>
