<script lang="ts">
  export let aboutMeRef: HTMLElement;

  const logos: { key: string; url: string }[] = [];
</script>

<section class="app-section" bind:this={aboutMeRef}>
  <div class="content">
    <h1 class="section-heading">ABOUT ME</h1>
    <p>I'm a full stack web developer with a background in real estate law and applied math.</p>
    <p>
      More than ten years ago my interest in coding led me to teach myself enough to code my first
      'app' -- a tool for automating case handling in my real estate practice. Ever since then
      I&rsquo;ve known coding was what I really want to do.
    </p>
    <p>
      I'm currrently a software engineer at <a href="https://www.filevine.com/" target="_blank"
        >Filevine</a
      >, doing fullstack work with Svelte, Javascript, and C#/ASP.Net And I have a portfolio of work
      with various clients and open source projects (check it out below!). I am continually seeking
      to expand my skills and knowledge and tackle new challenges.
    </p>
    <div class="logo-group">
      {#each logos as logo (logo.key)}
        <img src={logo.url} alt={logo.key} />
      {/each}
    </div>
  </div>
</section>

<style>
  section {
    background-color: #191919;
    color: #fff;
  }

  .content {
    max-width: 700px;
  }

  .logo-group {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }

  .logo-group img {
    height: 64px;
    margin-right: 24px;
    margin-top: 15px;
  }

  @media (max-width: 708px) {
    .logo-group img {
      height: 32px;
    }
  }
</style>
