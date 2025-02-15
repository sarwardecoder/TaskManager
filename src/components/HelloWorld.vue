

<script setup>
export default {
  data() {
    return {
      search: "",
      items: ["Apple", "Banana", "Cherry", "Date"]
    };
  },
  computed: {
    filteredItems() {
      return this.items.filter(item => item.toLowerCase().includes(this.search.toLowerCase()));
    }
  }
};
</script>
<template>
  <div>
    <input v-model="search" placeholder="Search...">
    <ul>
      <li v-for="item in filteredItems" :key="item">{{ item }}</li>
    </ul>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
