<template>
  <div>
    {{ data }}
  </div>
</template>

<script lang="ts" setup>

  const {id} = useRoute().params;
  const { data } = await useFetch(`https://dummyjson.com/users/${id as string}/posts`);
</script>

<style>

</style>