<script setup>
</script>

<template>
  <section id="design-space" class="construction-section">
    <img src="/public/design_space.png" alt="Construction design space" />
    <img src="/public/design_space2.png" alt="Construction design space" />
  </section>
</template>

<style scoped>
.construction-section {
  padding: 4rem 1rem;
  background-color: white;
  text-align: center;
  position: relative;
  overflow: hidden;
}

/* Add this new block specifically for your image */
.construction-section img {
  max-width: 100%; 
  height: auto; 
  object-fit: contain;
}

.content-box {
  max-width: 600px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}
</style>