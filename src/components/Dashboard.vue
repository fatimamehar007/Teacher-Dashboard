<template>
  <div class="dashboard">
    <h1>Teacher Dashboard</h1>

    <button @click="showParentSummary = true">View Parent Summary</button>
    <button @click="showNotifications = true">Notifications</button>
    <button @click="showTimeline = true">Activity Timeline</button>

    <ParentSummaryModal v-if="showParentSummary" @close="showParentSummary = false" />
    <NotificationDrawer v-if="showNotifications" @close="showNotifications = false" />
    <ActivityTimeline v-if="showTimeline" @close="showTimeline = false" />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import ParentSummaryModal from './ParentSummaryModal.vue'
import NotificationDrawer from './NotificationDrawer.vue'
import ActivityTimeline from './ActivityTimeline.vue'

const showParentSummary = ref(false)
const showNotifications = ref(false)
const showTimeline = ref(false)
</script>

<style scoped>
.dashboard {
  padding: 20px;
}
button {
  margin: 10px;
}
</style>
