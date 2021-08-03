<template>
  <div>
    <article-list v-if="isList()"/>
    <article-view v-if="isView()"/>
    <article-create v-if="isCreate()"/>
    <article-edit v-if="isEdit()"/>
  </div>
</template>

<script>

import ArticleList from "@/components/article/ArticleList";
import ArticleView from "@/components/article/ArticleView";
import ArticleCreate from "@/components/article/ArticleCreate";
import ArticleEdit from "@/components/article/ArticleEdit";

export default {
  name: 'Article',

  methods: {
    isCreate: function () {
      return this.$route.params.id === "" && this.$route.params.action.trim() === "create";
    },
    isEdit: function () {
      return this.$route.params.id !== "" && this.$route.params.action.trim() === "edit";
    },
    isView: function () {
      return this.$route.params.id !== "" && this.$route.params.action.trim() === "";
    },
    isList: function () {
      return this.$route.params.id === "" && this.$route.params.action.trim() === "";
    },
    t: function () {
      console.log(this.$route.params);
    }
  },

  components: {
    ArticleEdit,
    ArticleCreate,
    ArticleView,
    ArticleList,
  },
}
</script>
