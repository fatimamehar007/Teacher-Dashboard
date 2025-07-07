<template>
  <div class="drawer">
    <h4>Notifications</h4>
    <ul>
      <li>John Doe is struggling in Algebra. View AI recommendations.</li>
      <li>New Micro-PD available: Using formative assessment effectively.</li>
      <li>Your class engagement dropped 10% vs last week.</li>
    </ul>
    <button @click="$emit('close')">Close</button>
  </div>
</template>

<style scoped>
.drawer {
  position: fixed;
  top: 0; right: 0; height: 100%;
  width: 300px; background: #fff; box-shadow: -2px 0 5px rgba(0,0,0,0.2);
  padding: 20px;
}
</style>
