<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import CharactersList from "./components/CharactersList.vue";

export default {
  components: { AppHeader, AppMain, CharactersList },
};
</script>

<template>
  <AppHeader />
  <AppMain />
  <CharactersList />
</template>

<style lang="scss"></style>
