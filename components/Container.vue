<script lang="ts" setup>
interface ContainerProps {
  title: string;
  description?: string;
  class?: string;
}

const props = defineProps<ContainerProps>();

useHead({
  title: props.title,
  meta: [
    { name: "description", content: props.description },
    { property: "og:type", content: "website" },
    { property: "og:title", content: props.title },
    { property: "og:description", content: props.description },
    { name: "twitter:card", content: "summary_large_image" },
    { name: "twitter:title", content: props.title },
    { name: "twitter:description", content: props.description },
  ],
});
</script>

<template>
  <main id="page-container" :class="class">
    <slot />
  </main>
</template>
