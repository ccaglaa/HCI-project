<script setup>
import { ref, onMounted } from 'vue'

const rawNotes = [
  { img: "brainstorm/note1.jpeg", tags: ['least'] },
  { img: "brainstorm/note2.jpeg", tags: ['least'] },
  { img: "brainstorm/note3.jpeg", tags: ['sub'] },
  { img: "brainstorm/note4.jpeg", tags: ['least'] },
  { img: "brainstorm/note5.jpeg", tags: ['least'] },
  { img: "brainstorm/note6.jpeg", tags: [] },
  { img: "brainstorm/note7.jpeg", tags: [] },
  { img: "brainstorm/note8.jpeg", tags: ['most'] },
  { img: "brainstorm/note9.jpeg", tags: ['most'] },
  { img: "brainstorm/note10.jpeg", tags: ['most'] },
  { img: "brainstorm/note11.jpeg", tags: ['most'] },
  { img: "brainstorm/note12.jpeg", tags: [] },
  { img: "brainstorm/note13.jpeg", tags: ['most'] },
  { img: "brainstorm/note14.jpeg", tags: [] },
  { img: "brainstorm/note15.jpeg", tags: [] },
  { img: "brainstorm/note16.jpeg", tags: [] },
  { img: "brainstorm/note17.jpeg", tags: [] },
  { img: "brainstorm/note18.jpeg", tags: [] },
  { img: "brainstorm/note19.jpeg", tags: [] },
  { img: "brainstorm/note20.jpeg", tags: [] },
  { img: "brainstorm/note21.jpeg", tags: [] },
  { img: "brainstorm/note22.jpeg", tags: [] },
  { img: "brainstorm/note23.jpeg", tags: [] },
  { img: "brainstorm/note24.jpeg", tags: [] },
  { img: "brainstorm/note25.jpeg", tags: [] },
  { img: "brainstorm/note26.jpeg", tags: [] },
  { img: "brainstorm/note27.jpeg", tags: [] },
  // { title: "Extra Idea", desc: "Text fallback", tags: [] }, 
]

const brainstormNotes = ref([])

onMounted(() => {
  brainstormNotes.value = rawNotes.map(note => ({
    ...note,
    rotation: Math.random() * 6 - 3, 
  }))
})

const finalists = ref([
  { id: 1, text: "Smart Mirror", x: 80, y: 20 },
  { id: 2, text: "AI Stylist App", x: 90, y: 90 },
  { id: 3, text: "Paper Checklist", x: 10, y: 10 },
  { id: 4, text: "Consultant Call", x: 20, y: 80 },
  { id: 5, text: "Haptic Belt", x: 50, y: 30 },
  { id: 6, text: "VR Headset", x: 70, y: 95 }
])
</script>

<template>
  <div class="page-container">
    
    <section id="corkboard" class="corkboard-section">
      <div class="">
        <p class="subtitle">Sketches & Raw Ideas</p>
        
        <div class="legend">
          <div class="legend-item"><span class="tape-sample red"></span>Least Feasible</div>
          <div class="legend-item"><span class="tape-sample green"></span>Most Feasible</div>
          <!-- <div class="legend-item"><span class="dot-sample blue"></span> Subscription</div> -->
        </div>
      </div>

      <div class="notes-grid">
        <div 
          v-for="(note, index) in brainstormNotes" 
          :key="index" 
          class="sticky-item"
          :class="{ 'is-photo': note.img }"
          :style="{ transform: `rotate(${note.rotation}deg)` }"
        >
          <div v-if="note.tags.includes('least')" class="washi-tape red-tape"></div>
          <div v-if="note.tags.includes('most')" class="washi-tape green-tape"></div>
          <!-- <div v-if="note.tags.includes('sub')" class="blue-dot"></div> -->

          <img v-if="note.img" :src="note.img" class="note-photo" loading="lazy" />

          <div v-else class="text-content">
            <h3>{{ note.title }}</h3>
            <p>{{ note.desc }}</p>
          </div>

        </div>
      </div>
    </section>

    <!-- <section id="matrix" class="matrix-section">
      <div class="header-block">
        <h2>Phase 2: The Finalists</h2>
        <p class="subtitle">Design Space Analysis (Top 6)</p>
      </div>

      <div class="matrix-container">
        <span class="label top">Virtual / Digital</span>
        <span class="label bottom">Physical / Hardware</span>
        <span class="label left">Manual Effort</span>
        <span class="label right">Automated / AI</span>

        <div class="axis x-axis"></div>
        <div class="axis y-axis"></div>

        <div 
          v-for="item in finalists" 
          :key="item.id" 
          class="finalist-note"
          :style="{ left: item.x + '%', bottom: item.y + '%' }"
        >
          {{ item.text }}
        </div>
      </div>
    </section> -->

  </div>
</template>

<style scoped>
.page-container {
  background-color: white; 
  color: var(--text-dark);
  padding-bottom: 4rem;
}

.header-block {
  text-align: center;
  padding: 4rem 1rem 2rem;
}

h2 {
  font-size: 3rem;
  text-transform: uppercase;
  margin-bottom: 0.5rem;
}

.subtitle {
  font-size: 1.5rem;
  color: #666;
}

.legend {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 1.5rem;
}
.legend-item { display: flex; align-items: center; gap: 8px; font-family: 'Roboto Mono', monospace; font-size: 0.8rem; font-weight: bold; }
.tape-sample { width: 30px; height: 10px; display: block; opacity: 0.8; }
.red { background: #ff5e5e; }
.green { background: #5eff80; }
.dot-sample { width: 10px; height: 10px; border-radius: 50%; background: #5e80ff; display: block; border: 1px solid black; }

.notes-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 2rem;
  padding: 2rem;
  max-width: 1400px;
  margin: 0 auto;
}

.sticky-item {
  width: 180px;
  height: 180px;
  position: relative;
  transition: transform 0.2s ease;
  
  background-color: #fff475;
  border: 3px solid var(--text-dark);
  box-shadow: 6px 6px 0px rgba(0,0,0,1);
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 1rem;
}

.sticky-item.is-photo {
  background: white; 
  padding: 5px; 
  border: 1px solid #ccc; 
  box-shadow: 4px 4px 10px rgba(0,0,0,0.3); 
}

.note-photo {
  width: 100%;
  height: 100%;
  object-fit: cover; 
  display: block;
}

.sticky-item:hover {
  transform: scale(1.1) rotate(0deg) !important;
  z-index: 10;
  box-shadow: 10px 10px 20px rgba(0,0,0,0.5);
}

.washi-tape {
  position: absolute;
  width: 50px;
  height: 12px;
  top: -6px; 
  opacity: 0.9;
  mix-blend-mode: multiply;
  z-index: 5; 
}
.red-tape { background-color: #ff5e5e; left: 10px; transform: rotate(-3deg); }
.green-tape { background-color: #5eff80; right: 10px; transform: rotate(4deg); }
.blue-dot { position: absolute; bottom: 10px; right: 10px; width: 15px; height: 15px; background-color: #5e80ff; border-radius: 50%; border: 2px solid white; z-index: 5; }

.matrix-section {
  background: white;
  padding-bottom: 5rem;
  margin-top: 4rem;
  border-top: 3px dashed var(--text-dark);
}
.matrix-container {
  position: relative;
  width: 80%;
  max-width: 800px;
  height: 600px;
  margin: 0 auto;
  border: 4px solid var(--text-dark);
  border-radius: 4px;
  background: white;
  background-image: radial-gradient(#ddd 1px, transparent 1px);
  background-size: 20px 20px;
}
.axis { position: absolute; background: var(--text-dark); }
.x-axis { width: 100%; height: 3px; top: 50%; }
.y-axis { height: 100%; width: 3px; left: 50%; }
.label {
  position: absolute;
  font-family: 'Roboto Mono', monospace;
  text-transform: uppercase;
  font-weight: bold;
  font-size: 0.8rem;
  color: var(--text-dark);
  background: white;
  padding: 2px 8px;
  border: 1px solid var(--text-dark);
}
.top { top: -30px; left: 50%; transform: translateX(-50%); }
.bottom { bottom: -30px; left: 50%; transform: translateX(-50%); }
.left { top: 50%; left: -80px; transform: translateY(-50%) rotate(-90deg); }
.right { top: 50%; right: -80px; transform: translateY(-50%) rotate(90deg); }

.finalist-note {
  position: absolute;
  width: 110px;
  padding: 10px;
  background-color: #ffb7b2;
  color: black;
  font-family: 'Patrick Hand', cursive;
  font-weight: bold;
  font-size: 1rem;
  text-align: center;
  transform: translate(-50%, 50%);
  box-shadow: 4px 4px 0px black;
  border: 3px solid black;
  transition: z-index 0s;
}
.finalist-note:hover { z-index: 100; background-color: #ff9e99; }
</style>