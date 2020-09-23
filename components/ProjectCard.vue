<template>
  <div
    class="rounded overflow-hidden mt-6 shadow bg-gradient-to-br"
    :class="gradiantClasses"
  >
    <!--  -->
    <div class="md:flex">
      <div class="md:w-1/2 md:pt-12 md:pr-0 md:pl-8">
        <a
          class="block relative wiggle"
          :href="project.link"
          style="padding-top: 60%"
        >
          <img
            class="pin absolute block h-full w-full object-cover object-top rounded shadow-lg-dark"
            :src="project.imageUrl"
            :alt="project.imageAlt"
          />
        </a>
      </div>
      <div
        class="px-6 pt-6 pb-6 md:w-1/2 md:px-8 md:py-8 md:flex md:items-center"
      >
        <div>
          <div
            class="text-white text-xl md:text-2xl font-semibold tracking-tight leading-tight"
          >
            {{ project.title }}
          </div>
          <p
            class="mt-2 md:mt-3 text-sm md:text-md leading-itght font-medium md:leading-normal text-white opacity-75"
          >
            {{ project.description }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    project: {
      type: Object,
      required: true,
    },
  },
  computed: {
    gradiantClasses() {
      if (this.project.color === 'purple') {
        return `from-purple-300 via-purple-600 to-purple-800`;
      } else {
        return `from-green-300 via-green-600 to-green-800`;
      }
    },
  },
};
</script>

<style>
.pin {
  top: 5px;
  bottom: 0;
}
.wiggle {
  transition: 0.25s;
}

.wiggle:hover {
  transform: translateY(-4px);
}

.wiggle:focus {
  transform: translateY(-4px);
}

.shadow-lg-dark {
  @media (min-width: 768px) {
    -webkit-box-shadow: 0 5px 30px 0 rgba(0, 0, 0, 0.4),
      0 5px 15px 0 rgba(0, 0, 0, 0.2);
    box-shadow: 0 5px 30px 0 rgba(0, 0, 0, 0.4),
      0 5px 15px 0 rgba(0, 0, 0, 0.2);
  }
}
</style>
