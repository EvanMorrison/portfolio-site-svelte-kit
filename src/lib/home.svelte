<script lang="ts">
  export let homeRef: HTMLElement = null;
</script>

<section class="app-section" bind:this={homeRef}>
  <div class="title-section">
    <h1 class="main-title">Evan Morrison</h1>
    <h2 class="subtitle">Software Engineer / Web Developer</h2>
  </div>
</section>

<style>
  section {
    position: relative;
    height: 100vh;
    overflow: hidden;
  }

  section:after {
    position: absolute;
    z-index: -1;
    content: '';
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    width: 100%;
    height: 100%;
    transition: background 0.8s linear;
    background-image: url(https://i.imgur.com/1kzM2BN.jpg);
    filter: contrast(115%) opacity(0.9);
    background-position: center center;
    background-attachment: fixed;
    background-size: cover;
    background-repeat: no-repeat;
  }

  .title-section {
    position: relative;
    width: 90%;
    max-width: 500px;
    padding: 10px 20px 20px;
    border: 2px solid rgba(127, 125, 105, 0.8);
    background-color: rgba(230, 230, 230, 0.8);
    margin: 0 auto;
    box-shadow: 2px 2px 12px 3px rgba(0, 0, 0, 0.3);
  }

  .main-title {
    padding: 0;
    margin: 0;
    font-size: 3em;
    font-family: Roboto;
    font-weight: 100;
    text-align: center;
    text-shadow: 1px 1px 1px #555;
    color: #0a0a0a;
  }

  .subtitle {
    padding: 0;
    margin: 0;
    font-weight: 100;
    width: 100%;
    text-align: center;
    margin-top: 20px;
    text-shadow: 1px 1px 3px #555;
    color: #0a0a0a;
  }
</style>
