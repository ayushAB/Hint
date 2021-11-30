<template>
  <div class="relative">
    <span
      :class="`flex h-4 w-4 relative cursor-pointer ${rippleConfig.height}  ${rippleConfig.width}`"
      @click="onHintClick"
    >
      <span
        :class="`animate-ping absolute inline-flex h-full w-full rounded-full  opacity-75 ${rippleConfig.color}`"
      ></span>
      <span
        :class="`relative inline-flex rounded-full h-4 w-4 ${rippleConfig.color}`"
      ></span>
    </span>
    <diV
      :class="`text-gray-800 absolute top-5 transition-opacity duration-200 ease-in-out left-0 z-50 rounded px-3 py-4  w-72 shadow-2xl ${
        hintDailogConfig.backgroundColor
      } ${showHint ? 'opacity-100' : 'opacity-0'} `"
    >
      <p :class="` ${hintDailogConfig.hintTextColor} `">
        {{ hintDailogConfig.hintText }}
      </p>
      <div :class="`flex justify-${hintDailogConfig.buttonPostion}`">
        <button
          :class="`px-8 py-2 rounded ${hintDailogConfig.btnColor} ${hintDailogConfig.btnTextColor}`"
          @click="onHintButtonClick"
        >
          Next
        </button>
      </div>
    </diV>
  </div>
</template>

<script>
export default {
  props: {
    rippleConfig: {
      type: Object,
      default: () => {
        return {
          width: 'w-3',
          height: 'h-3',
          color: 'bg-green-400',
        }
      },
    },
    hintDailogConfig: {
      type: Object,
      default: () => {
        return {
          hintText: 'This is the Hint',
          buttonPostion: 'end',
          backgroundColor: 'bg-white',
          btnColor: 'bg-indigo-600',
          btnTextColor: 'text-white',
          hintTextColor: 'text-gray-800',
        }
      },
    },
  },
  data() {
    return {
      showHint: false,
    }
  },
  methods: {
    onHintClick() {
      this.showHint = !this.showHint
    },
    onHintButtonClick() {
      this.showHint = false
      this.$emit('hint-button-click')
    },
  },
}
</script>

<style></style>
