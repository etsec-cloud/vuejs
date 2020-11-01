<template>
  <div class="m-2">
    <base-button
      v-for="(bouton, index) in boutons"
      :key="index"
      @click="selectCompo(bouton.compo)"
      :text="bouton.text"
    >
    </base-button>

    <h1 class="text-xl font-bold">Liste des Équipes</h1>
    <component
      :is="selectedComponent"
      v-bind="currentProps"
      v-for="(equipe, index) in equipeData.equipes"
      :key="index"
      :equipe="equipe"
      @add-equipe="addPlayerToSelection"
      @supp-equipe="suppPlayerToSelection"
    ></component>
    <selection-equipe :list="list"></selection-equipe>
  </div>
</template>

<script>
import equipeData from "../assets/data/equipe.json";
import TeamCard from "./TeamCard.vue";
import TeamInfo from "./TeamInfo.vue";
import SelectionEquipe from "./SelectionEquipe";

export default {
  name: "team-list",
  components: {
    TeamCard,
    TeamInfo,
    SelectionEquipe
  },
  data() {
    return {
      equipeData: equipeData,
      selectedComponent: "team-card",
      list: [],
      boutons: [
        { text: "Info des équipes", compo: "team-info" },
        { text: "Moins d'info", compo: "team-card" }
      ]
    };
  },
  computed: {
    isDisabled() {
      if (this.list.lenght >= 1) {
        console.log("true");
        return true;
      }
      console.log("false");
      return false;
    }
  },
  methods: {
    selectCompo(comp) {
      this.selectedComponent = comp;
    },
    addPlayerToSelection(equipe) {
      this.list.push(equipe);
    },
    suppPlayerToSelection(equipe) {
      this.list.pop(equipe);
    }
  }
};
</script>

<style></style>
