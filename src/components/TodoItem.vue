<template>
  <div>
    {{ item.id }}. {{ item.name }}
    <div
      @click="onDelete(item.id)"
    >
      DELETE
    </div>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: String,
    },
    onDelete: {
      type: Function,
    },
  },
}
</script>

<style>
</style>
