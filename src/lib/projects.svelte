<script lang="ts">
  export let projectsRef: HTMLElement = null;
</script>

<section class="app-section" bind:this={projectsRef}>
  <div class="project-title-section">
    <h1 class="section-heading">SAMPLE PROJECTS</h1>
    <h2>Click a website image to visit the live site.</h2>
    <h2>Github icons are linked to the corresponding repo.</h2>
  </div>
  <div class="card-group" />
</section>

<style>
  section {
    padding-bottom: 200px;
    background-image: linear-gradient(rgba(200, 200, 200, 0.3), rgba(200, 200, 200, 0.3)),
      url(https://i.imgur.com/vmLotE1.jpg);
    background-size: cover;
    background-repeat: no-repeat;
    background-position: bottom center;
    background-attachment: fixed;
  }

  .project-title-section {
    width: 90%;
    max-width: 500px;
    padding: 10px 10px 30px;
    border: 2px solid rgba(127, 125, 105, 0.8);
    background-color: rgba(230, 230, 230, 0.8);
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .project-title-section h2 {
    margin: 0;
    font-weight: 100;
    font-size: 16px;
    text-align: center;
  }

  .card-group {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    padding-top: 30px;
    min-height: 50vh;
  }
</style>
