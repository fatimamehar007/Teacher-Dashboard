<template>
  <div class="modal">
    <div class="content">
      <h3>John Doe - Parent Summary</h3>
      <p><strong>Current Challenges:</strong> Algebra (65%)</p>
      <p><strong>Suggested Activities:</strong> 3 worksheets on factoring</p>
      <p><strong>Engagement:</strong> Logged in 2 times last week</p>
      <button>Download PDF</button>
      <button>Email to Parent</button>
      <button @click="$emit('close')">Close</button>
    </div>
  </div>
</template>

<style scoped>
.modal {
  position: fixed;
  top: 0; left: 0; right: 0; bottom: 0;
  background: rgba(0,0,0,0.5);
  display: flex; align-items: center; justify-content: center;
}
.content {
  background: white;
  padding: 20px;
  border-radius: 8px;
}
</style>
