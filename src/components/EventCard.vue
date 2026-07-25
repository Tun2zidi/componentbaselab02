<script setup lang="ts">
import type { Event } from '@/types'
import EventMeta from '@/components/EventMeta.vue'

defineProps<{
  event: Event
}>()
</script>

<template>
  <RouterLink class="event-link" :to ="{name: 'event-detail-view',params:{
    id: event.id
  }}">
  <div class="event-class">
    <h2>{{ event.title }}</h2>
    <span>@{{ event.time }} on {{ event.date }}</span>
    <EventMeta :event="event" />
    </div>
  </RouterLink>
  
</template>

<style scoped>
.event-class {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39395c;
  margin-bottom: 18px;
}

.event-class:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}

.event-link{
  text-decoration: none;
  color: #2c3e50;
}
</style>