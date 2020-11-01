<template>
  <button
    class="font-bold py-1 px-2 m-2 rounded bg-teal-700 text-white border-none hover:bg-teal-900"
  >
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "base-button",
  props: ["text"]
};
</script>

<style></style>
