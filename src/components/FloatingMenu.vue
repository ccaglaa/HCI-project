<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isVisible = ref(false)
const isOpen = ref(false)

const menuItems = [
  { label: 'Top', id: '#app' },
  { label: 'Interviews', id: '#interviews' },
  { label: 'Interactions', id: '#interactions' },
  { label: 'Personas', id: '#personas' },
  { label: 'Scenarios', id: '#scenarios' },
  { label: 'Brainstorm', id: '#corkboard' },
  { label: 'Design Space', id: '#design-space' }, 
  { label: 'Prototype', id: '#prototype' }
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

.fab-btn {
  background: white;
  border: 1px solid var(--text-dark); 
  border-radius: 8px; 
  box-shadow: 4px 4px 0px rgba(0,0,0,0.1); 
  font-family: 'Roboto Mono', monospace;
  font-weight: 700;
  text-transform: uppercase;
  font-size: 0.9rem;
  color: var(--text-dark);
  padding: 12px 24px; 
  cursor: pointer;
  transition: all 0.2s ease;
  display: flex;
  align-items: center;
  justify-content: center;
}

.fab-btn:hover {
  transform: translate(-2px, -2px);
  box-shadow: 6px 6px 0px rgba(0,0,0,0.15); 
  color: var(--pop-blue); 
  border-color: var(--pop-blue);
}

.fab-btn.active {
  background: var(--text-dark);
  color: white;
  box-shadow: none; 
  border-color: var(--text-dark);
}

.menu-list {
  background: white;
  border: 1px solid var(--text-dark); 
  border-radius: 8px;
  box-shadow: 4px 4px 0px rgba(0,0,0,0.1); 
  padding: 10px;
  display: flex;
  flex-direction: column;
  gap: 5px;
  min-width: 160px;
}

.menu-link {
  background: transparent;
  border: none;
  font-family: 'Roboto Mono', monospace; 
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