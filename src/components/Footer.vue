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
          <a href="https://github.com/ccaglaa/HCI-project" target="_blank" class="repo-link">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path>
            </svg>
            Source Code
          </a>
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

.repo-link {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  margin-top: 1rem;
  color: white;
  text-decoration: none;
  border: 1px solid white; 
  padding: 6px 14px;
  border-radius: 20px;
  font-size: 0.9rem;
  font-weight: 600;
  transition: all 0.2s ease;
  opacity: 0.9;
}
</style>