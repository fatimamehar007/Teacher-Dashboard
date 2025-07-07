<template>
  <div class="modal">
    <div class="content">
      <div class="header">
        <h3 class="title">  Parent Summary  </h3>
        <button class="close-btn" @click="$emit('close')">×</button>
      </div>

      <div class="body">
        <div v-if="!selectedStudent" class="student-selection">
          <h4 class="selection-title">Select Student:</h4>
          <div class="student-buttons">
            <button class="student-btn" @click="selectStudent('John Doe')">John Doe</button>
            <button class="student-btn" @click="selectStudent('Jane Smith')">Jane Smith</button>
            <button class="student-btn" @click="selectStudent('Alex Johnson')">Alex Johnson</button>
          </div>
        </div>

        <div v-if="selectedStudent">
          <h4 class="selected-student">{{ selectedStudent }}</h4>
          <div class="summary-content">
            <p class="summary-item"><strong>Current Challenges:</strong> Struggling with Algebra (current grade: 65%). Needs improvement in factoring and solving quadratic equations.</p>
            <p class="summary-item"><strong>Progress Insights:</strong> Consistent effort observed, with a 5% improvement over the last month. Areas for focus include consistent practice and understanding of key concepts.</p>
            <p class="summary-item"><strong>Suggested Activities:</strong> Complete 3 worksheets on factoring (available online), attend the upcoming Algebra support session on July 14, 2025, and review weekly progress with a tutor.</p>
            <p class="summary-item"><strong>Engagement:</strong> Logged in 2 times last week; encouraged to increase interaction with online resources for better outcomes.</p>
          </div>

          <div class="footer">
            <button class="action-btn download-btn">Download PDF</button>
            <button class="action-btn email-btn">Email to Parent</button>
            <button class="action-btn close-btn-modal" @click="$emit('close')">Close</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const selectedStudent = ref(null);

const selectStudent = (studentName) => {
  selectedStudent.value = studentName;
};
</script>

<style scoped>
.modal {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.content {
  background: #E6E6FA;
  padding: 25px;
  border-radius: 10px;
  width: 90%;
  max-width: 500px;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
  font-family: 'Inter', sans-serif;
}

.header {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
  position: relative;
}

.title {
  font-size: 1.5rem;
  font-weight: 700;
  color: #000000;
  margin: 0;
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


.close-btn:hover {
  color: #4B367C;
}

.selected-student {
  text-align: center;
  font-size: 1.3rem;
  font-weight: 700;
  color: #6B46C1;
  margin-bottom: 15px;
}

.body {
  margin-bottom: 20px;
}

.student-selection {
  margin-bottom: 15px;
}

.selection-title {
  font-size: 1.1rem;
  font-weight: 600;
  color: #000000;
  margin-bottom: 10px;
}

.student-buttons {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  justify-content: center;
}

.student-btn {
  padding: 6px 12px;
  border-radius: 8px;
  border: none;
  font-size: 0.9rem;
  font-weight: 600;
  background: #D1C4E9;
  color: #000000;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.student-btn:hover {
  background: #9575CD;
  color: #ffffff;
}

.student-btn:focus {
  outline: 2px solid #6B46C1;
  outline-offset: 2px;
}

.summary-content {
  margin-top: 15px;
}

.summary-item {
  font-size: 1rem;
  color: #000000;
  margin: 10px 0;
  line-height: 1.6;
}

.footer {
  display: flex;
  justify-content: space-between;
  gap: 10px;
}

.action-btn {
  flex: 1;
  padding: 6px 12px;
  border-radius: 8px;
  border: none;
  font-size: 0.9rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.download-btn {
  background: linear-gradient(90deg, #D1C4E9 0%, #9575CD 100%);
  color: #ffffff;
}

.download-btn:hover {
  background: linear-gradient(90deg, #9575CD 0%, #6B46C1 100%);
}

.email-btn {
  background: linear-gradient(90deg, #D1C4E9 0%, #9575CD 100%);
  color: #ffffff;
}

.email-btn:hover {
  background: linear-gradient(90deg, #9575CD 0%, #6B46C1 100%);
}

.close-btn-modal {
  background: linear-gradient(90deg, #EDE7F6 0%, #D1C4E9 100%);
  color: #000000;
}

.close-btn-modal:hover {
  background: linear-gradient(90deg, #D1C4E9 0%, #9575CD 100%);
}

.action-btn:focus {
  outline: 2px solid #6B46C1;
  outline-offset: 2px;
}
</style>
