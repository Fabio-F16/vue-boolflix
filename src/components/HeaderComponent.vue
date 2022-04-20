<template>
  <header>
    <input
      v-model="textToSearch"
      type="text"
      placeholder="Ricerca serie o film"
    />
    <button @click="$emit('searchEmit', textToSearch)">Cerca</button>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
  data() {
    return {
      textToSearch: "",
    };
  },
};
</script>

<style>
</style>