<script lang="ts" setup>
const { id } = useRoute().params;

const { data } = await useFetch(`https://dummyjson.com/users/${id as string}`);
</script>

<template>
  <UContainer>
    <div class="grid grid-cols-10 gap-4">
      <div class="col-span-3">
        <UCard>
          <UAvatar v-if="data.image" :src="data.image" />
          <h2>{{ data.firstName }} {{ data.lastName }}</h2>
          <p class="text-slate-500">
            {{ data.email }}
          </p>

          <UDivider class="my-4" />

          <div class="font-medium">links</div>

          <NuxtLink
            :to="{
              name: 'users-id-posts',
              params: { id: data.id },
            }"
            class="rounded border w-full py-2 px-4 block text-center mb-4"
            >Posts</NuxtLink
          >
          <NuxtLink
            :to="{
              name: 'users-id-todos',
              params: { id: data.id },
            }"
            class="rounded border w-full py-2 px-4 block text-center mb-4"
            >Todos</NuxtLink
          >
          <NuxtLink
            :to="{
              name: 'users-id-carts',
              params: { id: data.id },
            }"
            class="rounded border w-full py-2 px-4 block text-center"
            >Carts</NuxtLink
          >
        </UCard>
      </div>
      <UCard class="col-span-7">
        <NuxtPage :user="data" />
      </UCard>
    </div>
  </UContainer>
</template>

<style></style>
