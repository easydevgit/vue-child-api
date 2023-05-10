<script setup lang="ts">
import TimeMessage from '@/components/TimeMessage.vue';
const currentDate = new Date();
const eventDate = new Date(2024, 1, 1);

</script>
<template>
  <div>
    <TimeMessage
        :eventDate="eventDate"
        :currentDate="currentDate"
        v-slot="{days, hours, minutes}"
    >
      {{ days }} days, {{ hours }} hours, {{ minutes }} minutes
    </TimeMessage>
  </div>
</template>
