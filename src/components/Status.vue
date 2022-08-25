<template>
  <div class="px-3 h-6 rounded-full text-sm flex items-center text-white"
       :style="{backgroundColor: color}">
    <span>
      <slot></slot>
    </span>
  </div>
</template>
<script>
export default {
  name: "Status",
  props: {
    color: {
      type: String,
      default: ""
    }
  }
};
</script>
