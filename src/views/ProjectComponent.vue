<template>
  <div>
    <article-header-component :name="pageName"></article-header-component>
    <project-content-component></project-content-component>
    <footer-component></footer-component>
  </div>
</template>

<script>
import ArticleHeaderComponent from "../components/ArticleHeaderComponent.vue";
import ProjectContentComponent from "../components/ProjectContentComponent.vue";
import { mapMutations } from "vuex";
import FooterComponent from "@/components/FooterComponent.vue";

export default {
  components: {
    ArticleHeaderComponent,
    ProjectContentComponent,
    FooterComponent,
  },

  name: "ProjectComponent",

  data() {
    return {
      pageName: {
        header: "Our project",
        pagePath: "Project",
        id: 2,
      },
    };
  },

  methods: {
    ...mapMutations(["LOAD_PROJECT_PAGINATION"]),
  },

  beforeMount() {
    this.LOAD_PROJECT_PAGINATION();
  },
};
</script>

<style lang="scss" scoped>
@import "@/styles/_variables.scss";
@import "@/styles/_style_default.scss";
</style>
