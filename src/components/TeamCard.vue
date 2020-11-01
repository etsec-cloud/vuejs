<template>
  <div class="flex max-w-md justify-between">
    <img class="w-20" :src="equipeLogo(equipe.logo)" />
    {{ equipe.name }} <span class="text-xs">{{ equipe.type }} </span>
    <base-button text="Séléctionner" @click="addToSelection"></base-button>
    <base-button text="Supprimer" @click="suppToSelection"></base-button>
  </div>
</template>

<script>
export default {
  name: "team-card",
  props: ["equipe"],
  methods: {
    equipeLogo(img) {
      return require("@/assets/img/" + img);
    },
    addToSelection() {
      this.$emit("add-equipe", this.equipe);
    },
    suppToSelection() {
      this.$emit("supp-equipe", this.equipe);
    }
  }
};
</script>

<style></style>
