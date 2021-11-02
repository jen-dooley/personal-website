<template>
  <div
    class="relative overflow-hidden h-8 flex bg-gray-200 mb-3 text-white rounded"
  >
    <div
      class="absolute px-1 h-8 w-32 text-center font-semibold bg-purple-600"
    >
      {{ skill.title }}
    </div>
    <div
      class="bg-purple-300"
      :style="{ width: `${skill.proficiency}%` }"
    ></div>
    <div
      class="hidden md:block absolute right-0 pr-3 h-8 font-medium text-purple-900"
    >
      {{ skill.proficiency }}%
    </div>
  </div>
</template>

<script>
export default {
  props: {
    skill: {
      type: Object,
      required: true,
    },
  },
};
</script>
