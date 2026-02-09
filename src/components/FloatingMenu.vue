<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isVisible = ref(false)
const isOpen = ref(false)

// Make sure these IDs match your sections in Main.vue!
const menuItems = [
  { label: 'Top', id: '#app' },
  { label: 'Interviews', id: '#interviews' },
  { label: 'Personas', id: '#personas' },
  { label: 'Scenarios', id: '#scenarios' },
  { label: 'Brainstorm', id: '#corkboard' },
  { label: 'Design Space', id: '#matrix' }
]

const checkScroll = () => {
  isVisible.value = window.scrollY > 300
  if (window.scrollY <= 300) isOpen.value = false
}

const scrollToSection = (id) => {
  isOpen.value = false
  const element = document.querySelector(id)
  if (element) element.scrollIntoView({ behavior: 'smooth' })
}

onMounted(() => { window.addEventListener('scroll', checkScroll) })
onUnmounted(() => { window.removeEventListener('scroll', checkScroll) })
</script>

<template>
  <div class="floating-wrapper">
    
    <transition name="pop">
      <div v-if="isOpen" class="menu-list">
        <button 
          v-for="item in menuItems" 
          :key="item.label" 
          @click="scrollToSection(item.id)"
          class="menu-link"
        >
          {{ item.label }}
        </button>
      </div>
    </transition>

    <transition name="fade">
      <button 
        v-show="isVisible" 
        @click="isOpen = !isOpen" 
        class="fab-btn"
        :class="{ 'active': isOpen }"
      >
        <span v-if="!isOpen">MENU</span> <span v-else>CLOSE</span>
      </button>
    </transition>

  </div>
</template>

<style scoped>
.floating-wrapper {
  position: fixed;
  bottom: 30px;
  right: 20px;
  z-index: 9999;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 15px;
}

/* --- UPDATED BUTTON STYLE (Matches Header) --- */
.fab-btn {
  /* 1. Match the .nav-square background & border */
  background: white;
  border: 1px solid var(--text-dark); /* Thin border */
  border-radius: 8px; /* Square with slight round */
  
  /* 2. Match the .nav-square shadow */
  box-shadow: 4px 4px 0px rgba(0,0,0,0.1); 

  /* 3. Match the Typography */
  font-family: 'Roboto Mono', monospace;
  font-weight: 700;
  text-transform: uppercase;
  font-size: 0.9rem;
  color: var(--text-dark);

  /* Positioning */
  padding: 12px 24px; /* Slightly wider */
  cursor: pointer;
  transition: all 0.2s ease;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Hover Effect */
.fab-btn:hover {
  transform: translate(-2px, -2px);
  box-shadow: 6px 6px 0px rgba(0,0,0,0.15); /* Slightly deeper shadow */
  color: var(--pop-blue); /* Blue text on hover like header */
  border-color: var(--pop-blue);
}

/* Active State (When menu is open) */
.fab-btn.active {
  background: var(--text-dark);
  color: white;
  box-shadow: none; /* Flat when open */
  border-color: var(--text-dark);
}

/* --- MENU LIST STYLING (Updated to match) --- */
.menu-list {
  background: white;
  border: 1px solid var(--text-dark); /* Thin border */
  border-radius: 8px;
  box-shadow: 4px 4px 0px rgba(0,0,0,0.1); /* Light shadow */
  padding: 10px;
  display: flex;
  flex-direction: column;
  gap: 5px;
  min-width: 160px;
}

.menu-link {
  background: transparent;
  border: none;
  font-family: 'Roboto Mono', monospace; /* Changed to Roboto to match header */
  font-size: 0.9rem;
  font-weight: 600;
  text-align: right;
  padding: 8px 12px;
  cursor: pointer;
  transition: color 0.2s;
  color: var(--text-dark);
  text-transform: uppercase;
}

.menu-link:hover {
  color: var(--pop-blue);
  text-decoration: underline;
  text-decoration-thickness: 2px;
}

/* ANIMATIONS */
.fade-enter-active, .fade-leave-active { transition: opacity 0.3s; }
.fade-enter-from, .fade-leave-to { opacity: 0; }

.pop-enter-active { animation: bounce-in 0.3s; }
.pop-leave-active { animation: bounce-in 0.3s reverse; }

@keyframes bounce-in {
  0% { transform: scale(0.9); opacity: 0; }
  100% { transform: scale(1); opacity: 1; }
}

@media (max-width: 768px) {
  .floating-wrapper {
    bottom: 20px;
    right: 20px;
  }
}
</style>