<template>
  <div>
    {{ user }}
  </div>
</template>

<script lang="ts" setup>
const user = useAttrs().user;

const {} = useNuxtData
</script>

<style></style>
