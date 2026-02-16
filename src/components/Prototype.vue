<script setup>
// No logic needed yet, just a static placeholder
</script>

<template>
  <section class="prototype-section">
    <div class="header-block">
      <p class="subtitle">Video Demonstration</p>
    </div>

    <div class="video-container">
      <div class="video-frame">
        <div class="static-screen">
          <div class="overlay-msg">
            <span class="tape-strip"></span>
            <h3>[ FOOTAGE PENDING ]</h3>
            <p class="blink">_uploading_soon...</p>
          </div>
        </div>
      </div>
      
      <div class="decorative-blob"></div>
    </div>
  </section>
</template>

<style scoped>
.prototype-section {
  padding: 4rem 1rem 6rem;
  background-color: white; /* Changed from cream to white */
  text-align: center;
  position: relative;
  overflow: hidden;
}

.header-block {
  margin-bottom: 3rem;
}

h2 {
  font-size: 2.5rem;
  text-transform: uppercase;
  margin-bottom: 0.5rem;
}

.subtitle {
  font-family: 'Roboto Mono', monospace;
  color: #666;
  font-size: 1.2rem;
}

.video-container {
  position: relative;
  max-width: 800px;
  margin: 0 auto;
  z-index: 2;
}

.video-frame {
  background: var(--text-dark);
  padding: 1rem;
  border: 3px solid var(--text-dark); /* Standard 3px solid border */
  box-shadow: none;                   /* Removed the shadow */
  border-radius: 2px;
  aspect-ratio: 16 / 9;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.static-screen {
  width: 100%;
  height: 100%;
  background-color: #1a1a1a;
  background-image: 
    linear-gradient(45deg, #222 25%, transparent 25%, transparent 75%, #222 75%, #222),
    linear-gradient(45deg, #222 25%, transparent 25%, transparent 75%, #222 75%, #222);
  background-size: 20px 20px;
  background-position: 0 0, 10px 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  border: 2px solid #444;
}

.overlay-msg {
  background: white; /* Changed from cream to white */
  padding: 2rem 3rem;
  border: 3px solid var(--text-dark);
  transform: rotate(-2deg);
  /* Optional: removed shadow from the sticky note too, or keep for contrast? 
     I'll remove it to be safe based on "remove the shadow" */
  box-shadow: none; 
  position: relative;
}

.tape-strip {
  position: absolute;
  top: -15px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 20px;
  background-color: var(--pop-pink);
  opacity: 0.8;
  z-index: 5;
}

.overlay-msg h3 {
  margin: 0;
  font-size: 1.5rem;
  color: var(--text-dark);
}

.overlay-msg p {
  margin: 0.5rem 0 0;
  font-family: 'Roboto Mono', monospace;
  color: var(--pop-blue);
  font-weight: bold;
}

.blink {
  animation: blinker 1s linear infinite;
}

@keyframes blinker {
  50% { opacity: 0; }
}

.decorative-blob {
  position: absolute;
  top: -20px;
  right: -20px;
  width: 100px;
  height: 100px;
  background-color: var(--pop-lime);
  border-radius: 50%;
  border: 3px solid var(--text-dark);
  z-index: -1;
}
</style>