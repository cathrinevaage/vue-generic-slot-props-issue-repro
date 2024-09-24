<script
  setup
  lang="ts"
>
import ComponentWithGenericSlot from './ComponentWithGenericSlot.vue'

withDefaults(defineProps<(
  | { someProp: false }
  | { someProp: true }
)>(), {})

const items = [{
  id: 1,
  somePropertyNotInPropDefinition: 'foo'
}]
</script>

<template>
  <ComponentWithGenericSlot
    :items="items"
    v-slot="{ item }"
  >
    {{ item.somePropertyNotInPropDefinition }}
  </ComponentWithGenericSlot>
</template>
