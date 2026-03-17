<script setup>
// Logic for the Evaluation component
</script>

<template>
  <section class="evaluation-section">
    <div class="content-container">
      <div class="methodology-block">
        <h3>Our Approach: The Blind Test</h3>
        <p>
          To get the most honest feedback, we asked our interviewees to watch the video prototype <strong>without any prior explanation</strong> of what the product was. We wanted to see if the AR ecosystem and its features were intuitive enough to be understood through visual storytelling alone.
        </p>
      </div>

      <div class="grid-layout">
        <div class="card text-left">
          <h3>The Reality Check</h3>
          <p>The "blind watch" revealed that while the concept was intriguing, several visual cues were missing for a first-time viewer:</p>
          <ul>
            <li><strong>The "Bad Vision" Misconception:</strong> Testers thought the blurred billboards were just glare from a shiny surface, or that it implied the character had poor eyesight. They missed the ad-blocking feature entirely.</li>
            <li><strong>Identification Gap:</strong> Without an introduction, users couldn't distinguish between people wearing the lenses and those who were in unfiltered reality.</li>
            <li><strong>Spatial Safety Concerns:</strong> Users were worried that "blocking" ads might create dangerous blind spots in a busy city, potentially hiding traffic or hazards.</li>
          </ul>
        </div>

        <div class="card text-left">
          <h3>Our Response</h3>
          <p>Because the video didn't "speak for itself" perfectly, we implemented these key iterations:</p>
          <ul>
            <li><strong>Deliberate Censoring:</strong> We intensified the ad-blocker effect, changing it from a soft, shiny blur to a stark, obvious censor block so it clearly looks like an intentional software feature.</li>
            <li><strong>The Blue Indicator:</strong> We added a floating blue icon on active users to instantly and visually signify who is part of the shared AR ecosystem.</li>
            <li><strong>Selective Transparency:</strong> We refined the "censor" to be high-contrast but semi-transparent, ensuring toxic imagery is blocked while maintaining the user's peripheral awareness of their physical surroundings.</li>
          </ul>
        </div>
      </div>

      <div class="reflection-block">
        <h3>Final Reflection</h3>
        <p>
          This test proved that even the best technology needs clear <strong>visual signifiers</strong>. These iterations ensure that the user's motivation and the system's functions are undeniably clear from the very first second.
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.evaluation-section {
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

.content-container {
  max-width: 1000px;
  margin: 0 auto;
  color: #333;
  line-height: 1.6;
}

.methodology-block {
  background-color: #f0f4f8;
  padding: 2rem;
  border-left: 5px solid #dbff76;
  margin-bottom: 3rem;
  text-align: left;
}

.grid-layout {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  margin-bottom: 3rem;
}

@media (min-width: 768px) {
  .grid-layout {
    grid-template-columns: 1fr 1fr;
  }
}

.card {
  background-color: #f9f9f9;
  padding: 2rem;
  border-radius: 12px;
}

.text-left {
  text-align: left;
}

h3 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

ul {
  padding-left: 1.2rem;
}

li {
  margin-bottom: 0.8rem;
}

.reflection-block {
  background-color: #2d292bcc;
  color: #fff;
  padding: 2.5rem;
  border-radius: 12px;
  text-align: left;
}

.reflection-block h3 {
  color: #fff;
}
</style>