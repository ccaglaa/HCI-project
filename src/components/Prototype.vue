<script setup>
// No logic needed
</script>

<template>
  <section class="prototype-section">
    <div class="video-container">
      <div class="video-frame">
        
        <iframe 
          class="youtube-embed"
          src="https://www.youtube.com/embed/kB6fvV9ofP8?modestbranding=1&rel=0" 
          title="Prototype Video"
          frameborder="0" 
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
          referrerpolicy="strict-origin-when-cross-origin" 
          allowfullscreen
        ></iframe>

      </div>
      
      <div class="decorative-blob"></div>
    </div>
  </section>
</template>

<style scoped>
.prototype-section {
  padding: 4rem 1rem 6rem;
  background-color: white; 
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
  padding: 0;
  border: 3px solid var(--text-dark);
  box-shadow: none;
  border-radius: 4px;
  /* This forces the container to keep the 16:9 YouTube shape */
  aspect-ratio: 16 / 9; 
  position: relative;
  overflow: hidden;
}

.youtube-embed {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
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