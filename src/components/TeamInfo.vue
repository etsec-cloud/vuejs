<template>
  <div class="flex max-w-md justify-between">
    <p>{{ equipe.name }}</p>
    {{ equipe.country }} | {{ equipe.birthDate }} | {{ equipe.tournoisDone }} |
    {{ equipe.type }}
  </div>
</template>

<script>
export default {
  name: "team-info",
  props: ["equipe"],
  methods: {}
};
</script>

<style></style>
