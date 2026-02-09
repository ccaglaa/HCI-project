<script setup>
import { ref } from 'vue'

const episodes = ref([
  {
    id: 1,
    title: "Scenario 1:",
    setting: "📍 At home, on the couch.",
    context: "Everyone sees a viral post recommending a specific skincare product.",
    reactions: [
      {
        name: "Emily",
        color: "#ffb7b2", 
        action: "Realizes she has the specific problem mentioned in the post.",
        outcome: "Immediately starts researching ingredients and reviews."
      },
      {
        name: "Thomas",
        color: "#a0c4ff", 
        action: "Partner shows him the post to influence him.",
        outcome: "He ignores it. 'Too many steps.' Not interested in adding complexity."
      },
      {
        name: "Nara",
        color: "#bdb2ff", 
        action: "Realizes she already received this product in PR but never opened it.",
        outcome: "Sparked interest. Digs it out of her stash to use immediately."
      }
    ]
  },
  {
    id: 2,
    title: "Scenario 2: ",
    setting: "📍 Packing for a trip.",
    context: "Everyone is going on a trip (to South Korea)",
    reactions: [
      {
        name: "Emily",
        color: "#ffb7b2",
        action: "Realizes current products are too big for carry-on.",
        outcome: "Leaves them behind. Plans to buy brand new products in Korea."
      },
      {
        name: "Thomas",
        color: "#a0c4ff",
        action: "Traveling with just one backpack.",
        outcome: "Refuses to use space for skincare. Packs only cologne."
      },
      {
        name: "Nara",
        color: "#bdb2ff",
        action: "Packs a suitcase for products + a backpack for the plane.",
        outcome: "Buys a brand new suitcase just to fill with a haul from Korea."
      }
    ]
  }
])
</script>

<template>
  <section id="scenarios" class="scenarios-section">
    <div class="scenarios-container">
      <div v-for="ep in episodes" :key="ep.id" class="episode-block">
        
        <div class="episode-header">
          <div class="meta">
            <h3>{{ ep.title }}</h3>
            <span class="setting">{{ ep.setting }}</span>
          </div>
          <p class="context-text">{{ ep.context }}</p>
        </div>

        <div class="reaction-grid">
          <div 
            v-for="(react, index) in ep.reactions" 
            :key="index" 
            class="reaction-card"
            :style="{ borderTopColor: react.color }"
          >
            <span class="persona-name" :style="{ backgroundColor: react.color }">
              {{ react.name }}
            </span>
            <div class="card-content">
              <p><strong>Action:</strong> {{ react.action }}</p>
              <p class="outcome"><strong>Result:</strong> {{ react.outcome }}</p>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<style scoped>
.scenarios-section {
  padding: 4rem 1rem;
  max-width: 1100px;
  margin: 0 auto;
}

.header-block {
  text-align: center;
  margin-bottom: 4rem;
}

h2 {
  font-size: 3rem;
  text-transform: uppercase;
  margin-bottom: 0.5rem;
}

.subtitle {
  font-family: 'Patrick Hand', cursive;
  font-size: 1.5rem;
  color: #b1aeae;
}

.episode-block {
  margin-bottom: 5rem;
  border: 3px solid var(--text-dark);
  background: white;
  box-shadow: 8px 8px 0px rgba(0,0,0,0.1);
}

.episode-header {
  background: var(--bg-cream); 
  padding: 2rem;
  border-bottom: 3px solid var(--text-dark);
}

.meta {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 1rem;
  flex-wrap: wrap;
  gap: 10px;
}

.meta h3 {
  margin: 0;
  font-size: 1.5rem;
  text-transform: uppercase;
  background: #7b7b7b;
  color: white;
  padding: 5px 10px;
  display: inline-block;
  transform: none;
}

.setting {
  font-family: 'Roboto Mono', monospace;
  font-weight: bold;
  color: #555;
  font-size: 0.9rem;
}

.context-text {
  font-size: 1.1rem;
  margin: 0;
  max-width: 800px;
}

.reaction-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 0;
}

.reaction-grid .reaction-card {
  border-right: 3px solid var(--text-dark);
}

.reaction-grid .reaction-card:last-child {
  border-right: none;
}

.reaction-card {
  padding: 1.5rem;
  position: relative;
  background: white;
  border-top: 6px solid transparent; 
}

.persona-name {
  display: inline-block;
  padding: 4px 12px;
  font-weight: bold;
  text-transform: uppercase;
  font-size: 0.8rem;
  margin-bottom: 1rem;
  border: 2px solid var(--text-dark);
  box-shadow: 2px 2px 0px rgba(0,0,0,0.2);
}

.card-content p {
  margin: 0 0 1rem 0;
  line-height: 1.4;
  font-size: 0.95rem;
}

.outcome {
  margin-bottom: 0 !important;
  font-style: italic;
  color: #444;
  background: #f4f4f4;
  padding: 8px;
  border-radius: 4px;
}

@media (max-width: 768px) {
  .reaction-grid {
    grid-template-columns: 1fr;
  }

  .reaction-grid .reaction-card {
    border-right: none;
    border-bottom: 3px solid var(--text-dark);
  }

  .reaction-grid .reaction-card:last-child {
    border-bottom: none;
  }
}
</style>