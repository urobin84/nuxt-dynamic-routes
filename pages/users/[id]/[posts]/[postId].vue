<template>
  <div>
    {{ data }}
  </div>
</template>

<script lang="ts" setup>

  const {postId} = useRoute().params;
  const { data } = await useFetch(`https://dummyjson.com/posts/${postId as string}`);
</script>

<style>

</style>