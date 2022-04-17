<template>
  <div>{{ user }} Repositories</div>
</template>

<script>
export default {
  props: {
    user: {
      type: String,
      required: true,
    },
  },

  data() {
    return {
      repositories: [],
      filters: {},
      searchQuery: "",
    };
  },
  computed: {
    filteredRepositories() {
      return null;
    },

    repositoriesMatchingSearchQuery() {
      return null;
    },
  },
};
</script>

<style></style>
