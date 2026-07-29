<script setup lang="ts">
import { toRefs } from 'vue'
import type { Event } from '@/types'
import { storeToRefs } from 'pinia'
import { useMessageStore } from '@/stores/message'

const props = defineProps<{
  event: Event
}>()
const { event } = toRefs(props)

const store = useMessageStore()
const { message } = storeToRefs(store)
</script>

<template>
  <div v-if="message" class="update-message">
    <h4>{{ message }}</h4>
  </div>
  <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
  <p>{{ event.description }}</p>
</template>
