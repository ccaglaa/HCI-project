<script setup>
import { ref } from 'vue'

const scenarios = ref([
  {
    id: 1,
    title: "Impatience and Abandonment",
    icon: "〇",
    source: "Interview #4",
    color: "#ffb7b2", 
    panelA: { title: "Intent (Want)", text: "User feels insecure about a skin issue or is influenced by social media. They decide to start a routine to treat it." },
    panelB: { title: "Action (Clash)", text: "They apply it for a short period (1-2 weeks). The biological 'system' is slow and shows no immediate visible changes." },
    panelC: { title: "Result (Reaction)", text: "They lose patience, assuming it doesn't work. They stop using it, leaving the bottle unfinished and the problem unsolved." }
  },
  {
    id: 2,
    title: "Routine while traveling",
    icon: "〇",
    source: "Interview #1 & #6",
    color: "#dbff76", 
    panelA: { title: "Intent (Want)", text: "User is packing for a flight and wants to maintain their skin health while traveling." },
    panelB: { title: "Action (Clash)", text: "Essential bottles are too large for carry-on limits. Decanting is too much effort or simply not possible." },
    panelC: { title: "Result (Reaction)", text: "Forced to leave products at home. Resorts to hotel soap or partner's product (wrong skin type), breaking the routine." }
  },
  {
    id: 3,
    title: "Price vs Value",
    icon: "〇",
    source: "Interview #3 & #1",
    color: "#4d5ef0", 
    textColor: "white",
    panelA: { title: "Intent (Want)", text: "User sees a trending product (ex: Dior) on social media and feels the desire to buy it for the 'perfect' look." },
    panelB: { title: "Action (Clash)", text: "They check the price tag. The market 'system' creates a barrier that makes them question the investment." },
    panelC: { title: "Result (Reaction)", text: "They abandon the purchase, switching to a drugstore 'dupe' or giving up entirely." }
  },
  {
    id: 4,
    title: "Distractions while Waiting",
    icon: "〇",
    source: "Interview #1",
    color: "#ffdac1", 
    panelA: { title: "Intent (Want)", text: "User applies morning cream. Intends to follow the correct order: wash, cream, wait to dry, then sunscreen." },
    panelB: { title: "Action (Clash)", text: "Cream takes time to absorb. While waiting, the user leaves the bathroom to do something else due to hurry." },
    panelC: { title: "Result (Reaction)", text: "The distraction causes a memory lapse. They forget to return for sunscreen and leave unprotected." }
  },
  {
    id: 5,
    title: "Speed over skin",
    icon: "〇",
    source: "Interview #4 & #5",
    color: "#fdfbf7", 
    panelA: { title: "Intent (Want)", text: "User needs to shave facial hair quickly (under 5 mins) and wants to avoid mess." },
    panelB: { title: "Action (Clash)", text: "Uses razor without foam because previous products caused allergies. Shaves 'dry'." },
    panelC: { title: "Result (Reaction)", text: "Friction causes redness/irritation. They accept discomfort rather than adding a moisturizing step." }
  },
  {
    id: 6,
    title: "Incompatible Layering",
    icon: "〇",
    source: "Interview #3",
    color: "#ffb7b2", 
    panelA: { title: "Intent (Want)", text: "User wants to apply makeup over skincare to look natural and 'glowy'." },
    panelB: { title: "Action (Clash)", text: "Foundation applied over unabsorbed moisturizer. Products react chemically on the skin surface." },
    panelC: { title: "Result (Reaction)", text: "Makeup starts peeling or looking cakey. User frustrated, must wash face and restart entirely." }
  },
  {
    id: 7,
    title: "Convenient Substitution",
    icon: "〇",
    source: "Interview #4 & #1",
    color: "#dbff76", 
    panelA: { title: "Intent (Want)", text: "User feels dry or needs to wash, but has not invested effort in buying their own products." },
    panelB: { title: "Action (Clash)", text: "Instead of shopping, they 'steal' a pump of lotion from their partner's bottle on the shelf." },
    panelC: { title: "Result (Reaction)", text: "Uses product not designed for their skin type, but satisfied because it solved the problem with zero effort." }
  },
  {
    id: 8,
    title: "Indirect Influence",
    icon: "〇",
    source: "Interview #6",
    color: "#4d5ef0", 
    textColor: "white",
    panelA: { title: "Intent (Want)", text: "User needs a new skincare product but doesn't know what to choose." },
    panelB: { title: "Action (Clash)", text: "Instead of researching, they ask Mom. Mom gets her info from social media algorithms." },
    panelC: { title: "Result (Reaction)", text: "User blindly trusts and buys based on a 'secondary source,' removing themselves from the decision." }
  }
])
</script>

<template>
  <section id="interactions" class="interaction-section">
    <div v-for="item in scenarios" :key="item.id" class="storyboard-card">
      
      <div 
        class="card-header" 
        :style="{ backgroundColor: item.color, color: item.textColor || 'var(--text-dark)' }"
      >
        <div class="title-group">
          <span class="icon">{{ item.icon }}</span>
          <h3>{{ item.title }}</h3>
        </div>
        <span class="source-tag">{{ item.source }}</span>
      </div>

      <div class="comic-strip">
        
        <div class="panel">
          <div class="panel-label">A. Intent</div>
          <p>{{ item.panelA.text }}</p>
        </div>

        <div class="arrow">➜</div>

        <div class="panel">
          <div class="panel-label">B. Action</div>
          <p>{{ item.panelB.text }}</p>
        </div>

        <div class="arrow">➜</div>

        <div class="panel">
          <div class="panel-label">C. Result</div>
          <p>{{ item.panelC.text }}</p>
        </div>

      </div>
    </div>

  </section>
</template>

<style scoped>
.interaction-section {
  padding: 4rem 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.header-block {
  text-align: center;
  margin-bottom: 4rem;
}

h2 {
  font-size: 3rem;
  margin-bottom: 0.5rem;
  text-transform: uppercase;
  letter-spacing: -2px;
}

.subtitle {
  font-family: 'Patrick Hand', cursive;
  font-size: 1.5rem;
  color: #666;
}

.storyboard-card {
  border: 3px solid var(--text-dark);
  border-radius: 12px;
  background: white;
  box-shadow: 8px 8px 0px rgba(0,0,0,0.1); 
  margin-bottom: 3rem;
  overflow: hidden;
  transition: transform 0.2s;
}

.storyboard-card:hover {
  transform: translateY(-2px);
  box-shadow: 10px 10px 0px var(--text-dark);
}

.card-header {
  padding: 1rem 1.5rem;
  border-bottom: 3px solid var(--text-dark);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.title-group {
  display: flex;
  align-items: center;
  gap: 15px;
}

.card-header h3 {
  margin: 0;
  font-size: 1.2rem;
  text-transform: uppercase;
  letter-spacing: -0.5px;
}

.icon {
  font-size: 1.8rem;
}

.source-tag {
  font-family: 'Roboto Mono', monospace;
  font-size: 0.8rem;
  opacity: 0.8;
  border: 1px solid currentColor;
  padding: 2px 8px;
  border-radius: 20px;
}

.comic-strip {
  display: flex; 
  align-items: stretch;
  padding: 0;
}

.panel {
  flex: 1; 
  padding: 2rem;
  position: relative;
  background-image: radial-gradient(#ddd 1px, transparent 1px); /* Comic paper dots */
  background-size: 20px 20px;
}

.panel-label {
  font-family: 'Roboto Mono', monospace;
  font-weight: bold;
  font-size: 0.9rem;
  text-transform: uppercase;
  margin-bottom: 1rem;
  display: inline-block;
  background: #b0b0b0; 
  color: white;
  transform: none; 
  padding: 2px 8px;
}

.panel p {
  font-size: 1rem;
  line-height: 1.5;
  margin: 0;
}

.arrow {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  color: var(--text-dark);
  background: white;
  width: 40px;
  border-left: 3px solid var(--text-dark);
  border-right: 3px solid var(--text-dark);
  font-weight: bold;
}

@media (max-width: 768px) {
  .comic-strip {
    flex-direction: column;
  }
  
  .arrow {
    width: 100%;
    height: 40px;
    border-left: none;
    border-right: none;
    border-top: 3px solid var(--text-dark);
    border-bottom: 3px solid var(--text-dark);
    transform: rotate(90deg); 
  }

  .card-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 10px;
  }
}
</style>