<script setup>
import { ref } from 'vue'
import Interactions from './Interactions.vue';
import Personas from './Personas.vue';
import Scenarios from './Scenarios.vue'
import Brainstorming from './Brainstorming.vue';
import DesignSpace from './DesignSpace.vue';

const groupMembers = ref([
  {
    name: "Freyja",
    interviews: [
      { 
        id: 1, 
        age: 24, 
        nationality: "French", 
        sex: "M", 
        filename: "interviews/interview4.pdf" 
      },
      { 
        id: 2, 
        age: 23, 
        nationality: "Chinese", 
        sex: "F", 
        filename: "interviews/interview6.pdf" 
      }
    ]
  },
  {
    name: "Ale",
    interviews: [
      { 
        id: 3, 
        age: 15, 
        nationality: "Romanian", 
        sex: "F", 
        filename: "interviews/interview3.pdf" 
      },
      { 
        id: 4, 
        age: 22, 
        nationality: "Lithuanian", 
        sex: "M", 
        filename: "interviews/interview5.pdf" 
      }
    ]
  },
  {
    name: "Maria",
    interviews: [
        { 
        id: 5, 
        age: 54, 
        nationality: "Brazilian", 
        sex: "F", 
        filename: "interviews/interview1.pdf" 
      }
    ] 
  },
  {
    name: "Cagla",
    interviews: [
        { 
        id: 6, 
        age: 22, 
        nationality: "Turkish", 
        sex: "F", 
        filename: "interviews/interview2.pdf" 
      }
    ] 
  }
])
</script>

<template>
<main class="container">
    
    <section id="interviews">
      <h2>Project Team & Interviews</h2>
      <p>Click on an interview to view the transcript.</p>
      
      <div class="team-grid">
        <div v-for="member in groupMembers" :key="member.name" class="member-card">
          
          <div class="member-header">
            <h3>{{ member.name }}</h3>
            <span class="role">{{ member.role }}</span>
          </div>

          <div class="interview-list">
            <div v-if="member.interviews.length === 0" class="empty-state">
              No interviews yet.
            </div>

            <a 
              v-for="interview in member.interviews" 
              :key="interview.id"
              :href="interview.filename" 
              target="_blank" 
              class="interview-item"
            >
              <span class="icon">📄</span>
              <div class="details">
                <strong>{{ interview.subject }}</strong>
                <small>{{ interview.age }}yo • {{ interview.nationality }} • {{ interview.sex }}</small>
              </div>
            </a>
          </div>

        </div>
      </div>
    </section>

    <section id="interaction-points" class="placeholder-section">
      <h2>Interaction Points</h2>
      <Interactions />
    </section>

    <section id="personas" class="placeholder-section">
      <h2>Personas</h2>
      <Personas />
    </section>

    <section id="scenarios" class="placeholder-section">
      <h2>Scenarios</h2>
      <Scenarios />
    </section>

    <section id="brainstorming" class="placeholder-section">
      <h2>Brainstorming</h2>
      <Brainstorming />
    </section>

    <section id="design-space" class="placeholder-section">
      <h2>Design Space</h2>
      <DesignSpace />
    </section>

  </main>
</template>

<style scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}

/* Fun Section Headers */
h2 {
  font-size: 2.5rem;
  text-align: center;
  margin-bottom: 2rem;
  border-bottom: none; /* Remove the old line */
  position: relative;
  display: inline-block;
  width: 100%;
}

/* The squiggle underline effect */
h2::after {
  content: "";
  display: block;
  width: 100px;
  height: 10px;
  background: var(--pop-lime);
  margin: 0 auto;
  border-radius: 10px;
  margin-top: -10px;
  z-index: -1;
  transform: rotate(-2deg);
}

.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2.5rem;
}

/* THE STICKER CARD LOOK */
.member-card {
  background: white;
  border: 2px solid var(--text-dark);
  border-radius: 20px; /* Big rounded corners */
  padding: 1.5rem;
  box-shadow: 6px 6px 0px var(--text-dark); /* Hard drop shadow like a sticker */
  transition: transform 0.2s;
  position: relative;
}

/* Rotate every other card slightly for that "messy desk" look */
.member-card:nth-child(even) {
  transform: rotate(2deg);
}
.member-card:nth-child(odd) {
  transform: rotate(-2deg);
}

.member-card:hover {
  transform: rotate(0deg) scale(1.02);
  z-index: 10; /* Bring to front on hover */
}

/* Assign different colors to different cards (simulating the sticky notes) */
.member-card:nth-child(4n+1) { background-color: var(--pop-pink); }
.member-card:nth-child(4n+2) { background-color: var(--pop-blue); }
.member-card:nth-child(4n+3) { background-color: var(--pop-lime); }
.member-card:nth-child(4n+4) { background-color: var(--pop-orange); }

.member-header h3 {
  font-size: 1.8rem;
  margin: 0;
}

.role {
  background: white;
  padding: 4px 12px;
  border-radius: 50px;
  border: 1px solid var(--text-dark);
  font-size: 0.8rem;
  font-weight: bold;
}

/* INTERVIEW BUTTONS - Clean white pills to contrast with colorful cards */
.interview-item {
  display: flex;
  align-items: center;
  gap: 10px;
  background: white;
  padding: 12px;
  margin-top: 10px;
  border-radius: 15px;
  text-decoration: none;
  color: var(--text-dark);
  border: 2px solid transparent;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
  transition: all 0.2s;
}

.interview-item:hover {
  border-color: var(--text-dark);
  transform: scale(1.05);
}

/* Placeholders with dashed lines */
.placeholder-section {
  background: white;
  padding: 3rem;
  border: 3px dashed var(--text-dark);
  border-radius: 20px;
  text-align: center;
  margin-top: 4rem;
}
</style>