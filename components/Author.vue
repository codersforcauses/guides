<template>
  <div class="w-full xs:mb-6 md:mb-12 article-card">
    <NuxtLink
      :to="`/author/${author.name}`"
      class="flex flex-col dark:bg-black-dark"
    >
      <img
        v-if="author.img"
        loading="lazy"
        class="h-48 w-full object-cover"
        :src="author.img"
        :alt="`${author.name}'s photo`"
      />
      <div class="flex flex-col m-4">
        <h4 class="font-semibold">Author</h4>

        <p>{{ author.name }}</p>
        <p>{{ author.bio }}</p>
      </div>
    </NuxtLink>
  </div>
</template>

<script>
export default {
  props: {
    author: {
      type: Object,
      required: true
    }
  }
}
</script>
