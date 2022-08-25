<template>
  <div class="bg-white shadow rounded p-5 border-l-4"
  :style="{borderColor: color}">
    <div class="flex mb-4 justify-end items-center">
      <Status :color="badgeColor">{{ task.status }}</Status>
    </div>
    <div class="flex items-center mb-2">
      <img
          class="w-12 h-12 rounded-full mr-3"
          :src="task.avatar"
          alt="Avatar"
      >
      <div>
        <p class="text-sky-500 uppercase font-bold">{{ task.nickname }}</p>
        <p class="text-sky-400 font-bold">{{ task.email }}</p>
      </div>
    </div>
    <p class="text-gray-700 font-semibold font-sans tracking-wide text-sm mb-2 ">{{ task.title }}</p>
    <div class="flex justify-end items-center">
      <p class="font-medium text-sm">{{task.date}}</p>
    </div>
  </div>
</template>
<script>
import Status from "./Status";

export default {
  components: {
    Status
  },
  props: {
    task: {
      type: Object,
      default: () => ({})
    },
    color: {
      type: String,
      default: ""
    }
  },
  computed: {
    badgeColor() {
      const status = {
        'Low Priority': "rgb(52,168,30)",
        'Med Priority': "rgb(249,97,27)",
        'High Priority': "rgb(230,39,39)",
      };
      return status[this.task.status];
    }
  }
};
</script>
