<script lang="ts">
export default {
  emits: {
    userAction: null,
  },
  methods: {
    Cancel() {
      this.$emit("userAction", "");
    },
    setColor(uuid: number) {
      this.$emit("userAction", uuid);
    },
  },
};
</script>

<template>
  <div
    class="block fixed w-screen h-screen z-50 top-0 left-0 bg-black/50 dark:bg-white/25"
  >
    <div class="flex items-start mt-20 justify-center w-screen h-screen">
      <div class="bg-white dark:bg-neutral-800 p-2 rounded-lg drop-shadow">
        <h1 class="text-lg font-bold text-center">Choose color</h1>
        <div class="flex mb-2">
          <div
            class="h-8 m-1 aspect-square rounded-full hover:outline bg-red-400"
            @click="setColor(1)"
          ></div>
          <div
            class="h-8 m-1 aspect-square rounded-full hover:outline bg-green-400"
            @click="setColor(2)"
          ></div>
          <div
            class="h-8 m-1 aspect-square rounded-full hover:outline bg-blue-400"
            @click="setColor(3)"
          ></div>
          <div
            class="h-8 m-1 aspect-square rounded-full hover:outline"
            style="
              background: linear-gradient(
                90deg,
                rgba(0, 0, 0, 1) 0%,
                rgba(255, 255, 255, 1) 100%
              );
            "
            @click="setColor(0)"
          ></div>
        </div>
        <button
          class="select-none h-8 w-full px-3 py-1 bg-stone-200 dark:bg-neutral-900 rounded hover:outline hover:outline-2"
          @click="Cancel"
        >
          Cancel
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
@keyframes ScaleTrans {
  from {
    transform: scale(0, 0);
  }

  to {
    transform: scale(1, 1);
  }
}
</style>
