<script lang="ts">
  import type { Project } from './data/projectList';
  import { logoUrls } from './data/imgUrls';

  export let project: Project;
</script>

<div class="card-wrapper">
  <a class="project-link" href={project.siteUrl} target="_blank">
    <img src={project.imgUrl} alt={project.name} height="100%" width="100%" />
    <div class="overlay">
      <span>
        <div class="project-name">
          {project.name}
        </div>
        <span>
          {#each project.frameworks as logo (logo)}
            <img class="project-logos" src={logoUrls[logo]} alt={logo} title={logo} />
          {/each}
        </span>
      </span>
    </div>
  </a>
  <div class="github-link">
    <a href={project.gitUrl} target="_blank" title="view repo on Github">
      <img class="github-logo" src={logoUrls['Github']} alt="Github" />
    </a>
  </div>
</div>

<style>
  .card-wrapper {
    position: relative;
    flex: 1 0 40%;
    margin: 50px 8px 15px;
    min-width: 300px;
    max-width: 600px;
    will-change: contents;
    transform: scale(1);
    transition: all 0.2s ease-in-out;
    border-radius: 3px;
    overflow: hidden;
  }

  .card-wrapper:hover {
    transform: scale(1.005);
    box-shadow: 1px 1px 30px rgba(0, 0, 0, 0.4);
  }

  .project-link {
    text-decoration: none;
  }

  .overlay {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    padding: 3px;
    background: rgba(0, 0, 0, 0.4);
    color: #fff;
    height: 80px;
  }

  .project-name {
    font-size: calc(24 / 16 * 1rem);
  }

  .project-logos {
    margin: 0 4px;
    position: relative;
    top: 5px;
    height: 24px;
    background: #fff;
    border: 1px transparent;
    border-radius: 5px;
  }

  .github-link {
    position: absolute;
    bottom: 5px;
    right: 20px;
    z-index: 1000;
  }

  .github-logo {
    background: #fff;
    border-radius: 50%;
    height: 36px;
  }
</style>
