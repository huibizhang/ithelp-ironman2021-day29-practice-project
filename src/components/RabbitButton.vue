<template>
  <div
    :class="[
      'flex gap-2',
      'px-6 py-3',
      'rounded-md font-bold',
      'text-white',
      colorSelector,
      'hover:scale-105 active:scale-95',
      'transition-all',
      'cursor-pointer'
    ]"
  >
    <slot name="iconLeft" />
    {{ text }}
    <slot name="iconRight" />
  </div>
</template>

<script>
export default {
  name: "RabbitButton",
  props:{
    text: {
      default: "按鈕"
    },
    color: {
      default: "gray"
    },
  },
  computed: {
    colorSelector() {
      return {
        gray: 'bg-gray-400 hover:bg-gray-300 active:bg-gray-500',
        green: 'bg-green-400 hover:bg-green-300 active:bg-green-500',
        blue: 'bg-blue-400 hover:bg-blue-300 active:bg-blue-500',
        red: 'bg-red-400 hover:bg-red-300 active:bg-red-500',
        yellow: 'bg-yellow-400 hover:bg-yellow-300 active:bg-yellow-500',
      }[this.color]
    }
  }
}
</script>