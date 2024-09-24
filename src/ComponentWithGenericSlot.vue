<script
  setup
  lang="ts"
  generic="T extends { id: number }"
>
defineProps<{
  items: T[],
}>()

defineSlots<{
  default (props: {
    item: T,
  }): any
}>()
</script>

<template>
  <slot
    v-for="(item) in items"
    :item="item"
  />
</template>
