<script setup lang="ts">
const props = defineProps<{
  eventDate: Date,
  currentDate: Date
}>()

const getCalcRemainingTime = () => {
  const diff = props.eventDate.getTime() - props.currentDate.getTime()
  const minutes = Math.floor((diff / 1000 / 60) % 60)
  const hours = Math.floor((diff / (1000 * 60 * 60)) % 24)
  const days = Math.floor(diff / (1000 * 60 * 60 * 24))
  return {
    days,
    hours,
    minutes,
  }
}

defineExpose({
  getCalcRemainingTime
})

</script>
<template>
  <slot />
</template>
