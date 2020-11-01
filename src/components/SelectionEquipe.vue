<template>
  <div>
    Sélection {{ list.length }}
    <span v-if="nbfEquipe">equipes</span>
    <span v-else>equipe</span>
  </div>
</template>

<script>
export default {
  name: "equipe-selection",
  props: ["list"],
  computed: {
    nbfEquipe() {
      if (this.list.length > 1) {
        return true;
      }
      return false;
    }
  }
};
</script>

<style></style>
