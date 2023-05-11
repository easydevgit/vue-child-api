<script setup lang="ts">
import {onMounted, ref} from "vue";
import type {Ref} from 'vue'
import TimeMessage from '@/components/TimeMessage.vue';
import {DiffTime} from "@/types";

const currentDate = new Date();
const eventDate = new Date(2024, 1, 1);

const timeMessageRef = ref(null)
const diffTime: Ref<DiffTime | null> = ref(null)

onMounted(() => {
  diffTime.value = timeMessageRef.value.getCalcRemainingTime()
})

</script>
<template>
  <div>
    <TimeMessage
        :eventDate="eventDate"
        :currentDate="currentDate"
        ref="timeMessageRef"
    >
      {{ diffTime?.days }} days, {{ diffTime?.hours }} hours, {{ diffTime?.minutes }} minutes
    </TimeMessage>
  </div>
</template>
