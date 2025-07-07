<template>
  <div class="dashboard-wrapper bg-lavender min-h-screen w-full flex flex-col font-inter">
    <!-- Navigation Bar -->
    <nav class="navbar bg-purple-300 text-black py-5 shadow-lg">
      <div class="container mx-auto px-4 sm:px-6 lg:px-8 flex justify-between items-center">
        <div class="logo text-3xl font-extrabold tracking-wide font-inter">Teacher Dashboard</div>
        <div class="nav-links flex items-center space-x-6 sm:space-x-8">
 
          <button 
            class="nav-item text-black hover:text-purple-500 transition-all duration-300 text-lg sm:text-xl font-semibold px-6 py-3 rounded-lg hover:bg-purple-200 bg-purple-100"
            @click="toggleModal('parentSummary')"
          >
            Parent Summary
          </button>
          <button 
            class="nav-item text-black hover:text-purple-500 transition-all duration-300 text-lg sm:text-xl font-semibold px-6 py-3 rounded-lg hover:bg-purple-200 bg-purple-100 relative"
            @click="toggleModal('notifications')"
          >
            Notifications
            <span v-if="unreadNotifications > 0" 
                  class="absolute -top-2 -right-2 bg-red-600 text-white text-xs rounded-full px-2 py-1 font-medium">
              {{ unreadNotifications }}
            </span>
          </button>
          <button 
            class="nav-item text-black hover:text-purple-500 transition-all duration-300 text-lg sm:text-xl font-semibold px-6 py-3 rounded-lg hover:bg-purple-200 bg-purple-100"
            @click="toggleModal('timeline')"
          >
            Activity Timeline
          </button>
        </div>
      </div>
    </nav>

    <!-- Main Content -->
    <main class="container mx-auto px-4 sm:px-6 lg:px-8 py-10 flex-grow">
      <div class="dashboard-content bg-white rounded-xl p-6 sm:p-8 shadow-xl">
        <h2 class="text-3xl sm:text-4xl font-extrabold text-black mb-6">
          Welcome, {{ teacherFirstName || 'Name' }}!
        </h2>
        <p class="text-lg sm:text-xl text-black mb-8 max-w-2xl mx-auto leading-relaxed">
          Manage your classroom with powerful tools. Track student progress, communicate with parents, and monitor activities in real time.
        </p>

        <!-- Dashboard Features -->
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <!-- Total Stats - Activity -->
          <div class="feature-card bg-purple-50 rounded-xl p-5 flex flex-col items-center justify-center hover:shadow-xl transition-shadow duration-300">
            <h3 class="text-xl font-semibold text-black mb-3">Activity</h3>
            <p class="text-black text-base">75%</p>
            <div class="w-20 h-20 bg-purple-100 rounded-full flex items-center justify-center mt-3">
              <span class="text-3xl">📊</span>
            </div>
          </div>
          <!-- Total Stats - Task Completed -->
          <div class="feature-card bg-purple-50 rounded-xl p-5 flex flex-col items-center justify-center hover:shadow-xl transition-shadow duration-300">
            <h3 class="text-xl font-semibold text-black mb-3">Task Completed</h3>
            <p class="text-black text-base">9/12</p>
            <div class="w-20 h-20 bg-purple-100 rounded-full flex items-center justify-center mt-3">
              <span class="text-3xl">✅</span>
            </div>
          </div>
          <!-- Total Stats - Viewed Webinars -->
          <div class="feature-card bg-purple-50 rounded-xl p-5 flex flex-col items-center justify-center hover:shadow-xl transition-shadow duration-300">
            <h3 class="text-xl font-semibold text-black mb-3">Viewed Webinars</h3>
            <p class="text-black text-base">1/12</p>
            <div class="w-20 h-20 bg-purple-100 rounded-full flex items-center justify-center mt-3">
              <span class="text-3xl">🎥</span>
            </div>
          </div>
          <!-- Add a new category -->
          <div class="feature-card bg-purple-50 rounded-xl p-5 flex flex-col items-center justify-center hover:shadow-xl transition-shadow duration-300">
            <button class="bg-gradient-to-r from-purple-600 to-purple-700 text-white px-6 py-3 rounded-full text-base font-semibold hover:from-purple-700 hover:to-purple-800 transition-all duration-300 shadow-md">
              Add a new category
            </button>
          </div>
          <!-- Statistics of total class time -->
          <div class="feature-card bg-purple-50 rounded-xl p-5 col-span-2 hover:shadow-xl transition-shadow duration-300">
            <h3 class="text-xl font-semibold text-black mb-3">Statistics of total class time</h3>
            <div class="w-full h-48 flex items-center justify-center">
              <svg class="w-full h-full" viewBox="0 0 100 40">
                <path d="M10 30 Q20 10 30 20 Q40 30 50 10 Q60 20 70 30 Q80 10 90 20" fill="none" stroke="#6B46C1" stroke-width="2"/>
                <path d="M10 25 Q20 15 30 20 Q40 25 50 15 Q60 20 70 25 Q80 15 90 20" fill="none" stroke="#D1C4E9" stroke-width="2"/>
              </svg>
            </div>
            <p class="text-purple-700 text-base font-medium mt-3">6h : 2m 45s (17/01/2021)</p>
          </div>
          <!-- Class calendar -->
          <div class="feature-card bg-purple-50 rounded-xl p-5 hover:shadow-xl transition-shadow duration-300">
            <h3 class="text-xl font-semibold text-black mb-3">Class calendar</h3>
            <div class="grid grid-cols-7 gap-1.5 text-center text-black">
              <div>M</div><div>T</div><div>W</div><div>T</div><div>F</div><div>S</div><div>S</div>
              <div>1</div><div>2</div><div>3</div><div>4</div><div>5</div><div>6</div><div>7</div>
              <div>8</div><div>9</div><div>10</div><div>11</div><div>12</div><div>13</div><div>14</div>
              <div>15</div><div>16</div><div>17</div><div>18</div><div>19</div><div>20</div><div>21</div>
              <div>22</div><div>23</div><div>24</div><div>25</div><div>26</div><div>27</div><div>28</div>
              <div>29</div><div>30</div><div>31</div>
            </div>
            <div class="mt-3 p-3 bg-purple-100 rounded-xl">
              <p>Developer Meetup</p>
              <p>Meet world popular developers</p>
              <p>Sat, May 25, 2020</p>
              <p>10 AM to 6 PM</p>
              <p>Central Park, New York City</p>
            </div>
          </div>
          <!-- Popular Courses -->
          <div class="feature-card bg-purple-50 rounded-xl p-5 hover:shadow-xl transition-shadow duration-300">
            <h3 class="text-xl font-semibold text-black mb-3">Popular Courses</h3>
            <div class="flex flex-col space-y-3">
              <div class="flex items-center space-x-3">
                <span class="text-3xl">📝</span>
                <p>Technical SEO - 17 October 2021 - View 17 people</p>
                <button class="bg-gradient-to-r from-purple-600 to-purple-700 text-white px-4 py-2.5 rounded-full text-base font-semibold hover:from-purple-700 hover:to-purple-800 transition-all duration-300 shadow-md">
                  View Course
                </button>
              </div>
              <div class="flex items-center space-x-3">
                <span class="text-3xl">📈</span>
                <p>Marketing - 22 September 2021 - View 24 people</p>
                <button class="bg-gradient-to-r from-purple-600 to-purple-700 text-white px-4 py-2.5 rounded-full text-base font-semibold hover:from-purple-700 hover:to-purple-800 transition-all duration-300 shadow-md">
                  View Course
                </button>
              </div>
            </div>
          </div>
          <!-- Articles -->
          <div class="feature-card bg-purple-50 rounded-xl p-5 hover:shadow-xl transition-shadow duration-300">
            <h3 class="text-xl font-semibold text-black mb-3">Articles</h3>
            <div class="flex flex-col space-y-3">
              <div class="flex items-center space-x-3">
                
                <p>Marketing in digital world - Samuel Paddi</p>
              </div>
              <div class="flex items-center space-x-3">
                
                <p>The effect of noise on the human body. - Marry Cleary</p>
              </div>
              <button class="bg-gradient-to-r from-purple-600 to-purple-700 text-white px-4 py-2.5 rounded-full text-base font-semibold hover:from-purple-700 hover:to-purple-800 transition-all duration-300 shadow-md mt-3">
                See more
              </button>
            </div>
          </div>
        </div>
      </div>
    </main>

    <!-- Footer -->
    <footer class="bg-purple-800 text-white py-5">
      <div class="container mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <p class="text-base">© 2025 Teacher Dashboard. All rights reserved.</p>
      </div>
    </footer>

    <!-- Modals / Drawers -->
    <transition name="fade">
      <ParentSummaryModal
        v-if="showParentSummary"
        @close="toggleModal('parentSummary')"
      />
    </transition>
    <transition name="slide">
      <NotificationDrawer
        v-if="showNotifications"
        @close="toggleModal('notifications')"
        @notification-read="decrementNotifications"
      />
    </transition>
    <transition name="fade">
      <ActivityTimeline
        v-if="showTimeline"
        @close="toggleModal('timeline')"
      />
    </transition>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import ParentSummaryModal from './ParentSummaryModal.vue';
import NotificationDrawer from './NotificationDrawer.vue';
import ActivityTimeline from './ActivityTimeline.vue';

const showParentSummary = ref(false);
const showNotifications = ref(false);
const showTimeline = ref(false);
const unreadNotifications = ref(3); // Simulated unread notifications
const teacherFirstName = ref(''); // Placeholder for dynamic name

const toggleModal = (modal) => {
  showParentSummary.value = modal === 'parentSummary' ? !showParentSummary.value : false;
  showNotifications.value = modal === 'notifications' ? !showNotifications.value : false;
  showTimeline.value = modal === 'timeline' ? !showTimeline.value : false;
};

const decrementNotifications = () => {
  if (unreadNotifications.value > 0) {
    unreadNotifications.value--;
  }
};
</script>

<style scoped>
/* Custom animations for modals and drawers */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.4s ease-in-out;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.slide-enter-active,
.slide-leave-active {
  transition: transform 0.4s ease-in-out;
}
.slide-enter-from,
.slide-leave-to {
  transform: translateX(100%);
}

/* Ensure buttons are accessible */
button:focus,
.router-link-active:focus {
  outline: 2px solid #D1C4E9;
  outline-offset: 2px;
}

/* Feature card styling */
.feature-card {
  transition: box-shadow 0.3s ease-in-out;
}
.feature-card:hover {
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.15);
}

/* Navigation link active state */
.router-link-active {
  background-color: #D1C4E9;
  color: #ffffff;
}

/* Font definitions */
.font-inter {
  font-family: 'Inter', sans-serif;
}

/* Custom colors */
.bg-lavender {
  background-color: #E6E6FA;
}
</style>