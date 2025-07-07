<template>
  <div class="drawer">
    <div class="header">
      <h4>Notifications</h4>
      <button class="close-btn" @click="$emit('close')">×</button>
    </div>
    <ul class="notification-list">
      <li>📊 John Doe is struggling in Algebra. View AI recommendations.</li>
      <li>📝 New Micro-PD: Using formative assessment effectively.</li>
      <li>📉 Class engagement dropped 10% vs last week.</li>
    </ul>
  </div>
</template>

<style scoped>
.drawer {
  position: fixed;
  top: 0; right: 0; height: 100%;
  width: 320px;
  background: #fdfaff;
  box-shadow: -2px 0 10px rgba(0,0,0,0.2);
  padding: 20px;
  font-family: 'Inter', sans-serif;
  display: flex;
  flex-direction: column;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
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
  font-size: 1.3rem;
  font-weight: 600;
  color: #302453;
}

.notification-list {
  list-style: none;
  padding: 0;
}

.notification-list li {
  background: #e6e0f8;
  margin-bottom: 10px;
  padding: 10px 12px;
  border-radius: 6px;
  font-size: 0.95rem;
  color: #302453;
}
</style>
