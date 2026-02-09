<script setup>
import { ref } from 'vue'

const personas = ref([
  {
    id: 1,
    name: "Emily",
    details: "25 years old, Graduate",
    color: "#ffb7b2", 
    image: "personas/emily.jpg", 
    bio: "She has been using skincare consistently since she was 15. She had severe acne when she was a teenager. She used to take medicine for that, now she only uses skincare out of habit and to keep problems from reappearing. She has mixed skin type. She prefers drugstore products. She hasn't been to the dermatologist since she stopped taking Accutane. She wore more makeup when she had acne, now she wears light makeup daily. She lives with 5 roommates and she doesn't share products with them, but her roommates sometime steal her products."
  },
  {
    id: 2,
    name: "Thomas",
    details: "22 years old, Student",
    color: "#a0c4ff", 
    image: "personas/thomas.jpg",
    bio: "He doesn't use skin care regularly, he's not opposed to it, but he just doesn't have the necessary patience and he thinks it's too expensive. He mainly uses cleanser, lotion and cologne. He got a gift from Oras and he used it, but he didn't buy it again even though he found it useful. He doesn't know what type of skin he has. He lives with his partner who does use skincare and they do skincare together sometimes (masks) when his partner comes with the initiative. He enjoys it but it doesn't become a routine."
  },
  {
    id: 3,
    name: "Nara",
    details: "37 years old, Influencer",
    isExtreme: true,
    color: "#bdb2ff",
    image: "personas/nara.jpg",
    bio: "She's afraid of aging. She has done procedures at skincare clinics to look younger. She travels a lot and she brings all of her products with her, she has a whole carry on only for that. She once traveled to Korea for a procedure. She gets a lot of products from PR but she rarely uses them. She likes specific, expensive products that she buys herself. She has dry skin. She lives in California and she uses an umbrella in the sun. She goes to botox parties. She uses a lot of makeup."
  }
])
</script>

<template>
  <section id="personas" class="personas-section">
    
    <div class="list-container">
      <div 
        v-for="person in personas" 
        :key="person.id" 
        class="persona-ticket"
        :class="{ 'extreme-ticket': person.isExtreme }"
      >
        <div v-if="person.isExtreme" class="extreme-badge">EXTREME USER</div>

        <div class="ticket-sidebar" :style="{ backgroundColor: person.color }">
          <div class="portrait-frame">
            <img :src="person.image" :alt="person.name" class="sketch-img" />
          </div>
          <h3 class="name">{{ person.name }}</h3>
          <span class="details">{{ person.details }}</span>
          </div>

        <div class="ticket-content">
          <p class="bio-text">"{{ person.bio }}"</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.personas-section {
  padding: 2rem 1rem; 
  max-width: 1000px;
  margin: 0 auto;
}

.list-container {
  display: flex;
  flex-direction: column;
  gap: 3rem;
}

.persona-ticket {
  display: flex;
  border: 3px solid var(--text-dark);
  border-radius: 12px;
  background: white;
  box-shadow: 8px 8px 0px rgba(0,0,0,0.1);
  overflow: hidden;
  position: relative;
  min-height: 280px; 
}

.extreme-ticket {
  border: 3px solid #6a4c93;
}

.extreme-badge {
  position: absolute;
  top: 0;
  right: 0;
  background: #ff0055;
  color: white;
  padding: 5px 15px;
  font-size: 0.7rem;
  font-weight: bold;
  border-bottom-left-radius: 8px;
  z-index: 10;
  border-left: 3px solid var(--text-dark);
  border-bottom: 3px solid var(--text-dark);
}

.ticket-sidebar {
  width: 35%; 
  min-width: 240px;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  border-right: 3px solid var(--text-dark);
  flex-shrink: 0;
  justify-content: center;
}

.portrait-frame {
  width: 180px; 
  height: 220px; 
  background: white;
  border: 3px solid var(--text-dark);
  border-radius: 8px;
  overflow: hidden;
  margin-bottom: 1rem;
  box-shadow: 4px 4px 0px rgba(0,0,0,0.2);
}

.sketch-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.name {
  font-size: 2rem;
  margin: 0;
  line-height: 1;
}

.details {
  font-family: 'Roboto Mono', monospace;
  font-size: 0.9rem;
  margin-top: 5px;
  opacity: 0.8;
  font-weight: bold;
}

.ticket-content {
  padding: 2.5rem;
  flex-grow: 1;
  display: flex;
  align-items: center; 
}

.bio-text {
  font-size: 1.1rem;
  line-height: 1.6;
  color: #333;
  margin: 0;
  font-style: italic; 
}

@media (max-width: 768px) {
  .persona-ticket {
    flex-direction: column;
  }
  
  .ticket-sidebar {
    width: 100%;
    border-right: none;
    border-bottom: 3px solid var(--text-dark);
    padding: 1.5rem;
  }

  .portrait-frame {
    width: 150px;
    height: 180px;
  }

  .ticket-content {
    padding: 1.5rem;
  }
  
  .bio-text {
    font-size: 1rem;
  }
}
</style>