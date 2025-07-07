<template>
  <div class="timeline">
    <h4>Activity History</h4>
    <ul>
      <li>July 6 - John completed Algebra worksheet 2.</li>
      <li>July 5 - AI recommended Algebra practice based on quiz.</li>
      <li>July 3 - Teacher assigned Geometry micro-PD.</li>
      <li>July 1 - Engagement dip detected for John.</li>
    </ul>
    <button @click="$emit('close')">Close</button>
  </div>
</template>

<style scoped>
.timeline {
  position: fixed;
  top: 20%;
  left: 50%; transform: translateX(-50%);
  background: #b23434;
  padding: 20px; border: 1px solid #ccc; border-radius: 8px;
}
</style>
