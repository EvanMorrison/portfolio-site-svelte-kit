<script lang="ts">
  import { logoUrls } from './data/imgUrls';
  import AboutMeLogo from './aboutMeLogo.svelte';

  export let aboutMeRef: HTMLElement = null;
  export let sectionNum: number;
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
      >, doing full-stack work with Svelte, Javascript, and C#/ASP.Net. I have a portfolio of work
      from a variety of projects (check it out below!). I am continually seeking to expand my skills
      and knowledge and tackle new challenges.
    </p>
    <div class="logo-group">
      {#each Object.values(logoUrls).slice(0, 19) as logo (logo)}
        <AboutMeLogo {logo} {sectionNum} {aboutMeRef} />
      {/each}
    </div>
  </div>
</section>

<style>
  section {
    background-color: #191919;
    color: #fff;
    overflow: hidden;
  }

  .content {
    max-width: 700px;
  }

  a,
  a:visited {
    color: #f58;
  }

  .logo-group {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
</style>
