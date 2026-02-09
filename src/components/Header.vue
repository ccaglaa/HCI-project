<script setup>
</script>

<template>
  <header class="site-header">
    <div class="logo">
      HCI Project <span>:)</span>
    </div>
    
    <nav class="nav-square">
      <a href="#interviews" class="nav-link">Interviews</a>
      <a href="#interaction-points" class="nav-link">Interactions</a>
      <a href="#personas" class="nav-link">Personas</a>
      <a href="#scenarios" class="nav-link">Scenarios</a>
      <a href="#brainstorming" class="nav-link">Brainstorming</a>
    </nav>

    </header>
</template>

<style scoped>
.site-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.5rem 2rem;
  background-color: transparent;
}

/* LOGO: Bold and Strong (Roboto Mono) */
.logo {
  font-family: 'Roboto Mono', monospace; /* The strong previous font */
  font-size: 1.5rem;
  font-weight: 700; /* Extra Bold */
  text-transform: uppercase;
  color: var(--text-dark);
  cursor: pointer;
  letter-spacing: -1px;
}

.logo span {
  color: var(--pop-blue);
}

/* MENU: Square style instead of round pill */
.nav-square {
  display: flex;
  gap: 2rem; /* More space between links */
  background: white;
  padding: 0.8rem 2rem;
  
  /* The "Square" look (same as the old contact button) */
  border-radius: 8px; 
  border: 1px solid var(--text-dark);
  
  /* Hard shadow for the sticker/pop vibe */
  box-shadow: 4px 4px 0px rgba(0,0,0,0.1); 
}

.nav-link {
  text-decoration: none;
  color: var(--text-dark);
  font-weight: 600;
  font-size: 0.9rem;
  position: relative;
  text-transform: uppercase;
}

.nav-link:hover {
  color: var(--pop-blue);
  text-decoration: underline;
  text-decoration-thickness: 2px;
}
</style>