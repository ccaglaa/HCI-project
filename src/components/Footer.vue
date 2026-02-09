<script setup>
</script>

<template>
  <footer class="site-footer">
    <div class="footer-content">
      
      <div class="footer-columns">
        <div class="col">
          <h4>Project</h4>
          <p>HCI</p>
          <p>Sorbonne Université</p>
        </div>
        <div class="col">
          <h4>Team</h4>
          <p>Ale • Freyja</p>
          <p>Maria • Cagla</p>
        </div>
        <div class="col">
          <h4>Prof</h4>
          <p>Gilles Bailly</p>
        </div>
      </div>

      <div class="big-text">
        THANKS FOR VISITING
        <span class="sticker">★</span>
      </div>
      
    </div>
  </footer>
</template>

<style scoped>
.site-footer {
  margin-top: 4rem;
  background-color: var(--pop-blue); 
  color: white;
  border-top-left-radius: 40px;
  border-top-right-radius: 40px;
  padding: 4rem 2rem 2rem 2rem;
  position: relative;
}

.footer-columns {
  display: flex;
  justify-content: space-between;
  max-width: 1200px;
  margin: 0 auto 4rem auto;
  flex-wrap: wrap;
  gap: 2rem;
}

.col h4 {
  background: white;
  color: var(--pop-blue);
  display: inline-block;
  padding: 5px 10px;
  border-radius: 20px;
  font-size: 0.9rem;
  margin-bottom: 1rem;
  text-transform: uppercase;
}
 
.col p {
  margin: 0.5rem 0;
  font-size: 1.1rem;
}

.big-text {
  font-family: 'Patrick Hand', cursive;
  font-size: clamp(3rem, 10vw, 8rem); 
  text-align: center;
  line-height: 0.9;
  opacity: 0.9;
  margin-top: 2rem;
  position: relative;
}

.sticker {
  color: var(--pop-lime);
  position: absolute;
  top: -20px;
  right: 10%;
  font-size: 0.5em;
  transform: rotate(15deg);
}
</style>