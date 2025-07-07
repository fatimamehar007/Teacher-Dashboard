<template>
  <div class="timeline">
    <div class="header">
      <h4>Activity History</h4>
      <button class="close-btn" @click="$emit('close')">×</button>
    </div>
    <ul class="timeline-list">
      <li>📅 July 6 - John completed Algebra worksheet 2.</li>
      <li>🤖 July 5 - AI recommended Algebra practice.</li>
      <li>📚 July 3 - Teacher assigned Geometry micro-PD.</li>
      <li>⚠️ July 1 - Engagement dip detected for John.</li>
    </ul>
  </div>
</template>

<style scoped>
.timeline {
  position: fixed;
  top: 20%;
  left: 50%;
  transform: translateX(-50%);
  background: linear-gradient(135deg, #6B46C1 0%, #9575CD 100%);
  color: #fff;
  padding: 25px;
  border-radius: 10px;
  width: 90%;
  max-width: 400px;
  box-shadow: 0 8px 20px rgba(0,0,0,0.3);
  font-family: 'Inter', sans-serif;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
}

.close-btn {
  font-size: 1.5rem;
  font-weight: 600;
  background: none;
  border: none;
  color: #6B46C1;
  cursor: pointer;
  padding: 2px 6px;
  line-height: 1;
  margin-left: 12px; /* move it slightly to the right */
  transition: color 0.3s ease;
}


h4 {
  font-size: 1.4rem;
  font-weight: 700;
  margin: 0;
}

.timeline-list {
  list-style: none;
  padding: 0;
}

.timeline-list li {
  background: rgba(255,255,255,0.15);
  padding: 10px;
  margin-bottom: 8px;
  border-radius: 6px;
  font-size: 0.95rem;
}
</style>
