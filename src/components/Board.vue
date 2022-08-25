<template>
  <div class="bg-white p-3 m-5 column-width rounded drop-shadow-xl border-t-4">
    <p class="text-gray-700 font-semibold font-sans tracking-wide text-lg uppercase">{{ title }}: ({{ taskLength }})</p>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Board.vue",
  props: {
    title: {
      type: String,
      default: 'test'
    },
    taskLength: {
      type: Number,
      default: 0
    },
  },
}
</script>
