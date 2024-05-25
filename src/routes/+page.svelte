<script lang="ts">
  import '../app.css';
  import Menu from '$lib/menu.svelte';
  import Home from '$lib/home.svelte';
  import AboutMe from '$lib/aboutMe.svelte';
  import Contact from '$lib/contact.svelte';
  import Projects from '$lib/projects.svelte';

  let homeRef: HTMLElement;
  let aboutMeRef: HTMLElement;
  let contactRef: HTMLElement;
  let projectsRef: HTMLElement;
  let sectionNum = 0;
  let backgroundDark = false;

  const handleMenuClick = (el: HTMLElement) => {
    if (!el) window.location.reload();
    el.scrollIntoView({ behavior: 'smooth', block: 'start' });
  };

  const scrollHandler = () => {
    if (projectsRef?.getBoundingClientRect().top < 30) {
      backgroundDark = true;
      sectionNum = 4;
    } else if (contactRef?.getBoundingClientRect().top < 30) {
      backgroundDark = false;
      sectionNum = 3;
    } else if (aboutMeRef?.getBoundingClientRect().top < 30) {
      backgroundDark = true;
      sectionNum = 2;
    } else if (homeRef?.getBoundingClientRect()) {
      backgroundDark = false;
      sectionNum = 1;
    } else {
      window.location.reload();
    }
  };
</script>

<svelte:window on:scroll={scrollHandler} />

<Menu onDark={backgroundDark} {sectionNum}>
  <li class:active={sectionNum === 1}><div on:click={() => handleMenuClick(homeRef)} on:keyup role="button" tabindex="0">Top</div></li>
  <li><div class:active={sectionNum === 2} on:click={() => handleMenuClick(aboutMeRef)} on:keyup role="button" tabindex="0">About</div></li>
  <li><div class:active={sectionNum === 3} on:click={() => handleMenuClick(contactRef)} on:keyup role="button" tabindex="0">Contact</div></li>
  <li><div class:active={sectionNum === 4} on:click={() => handleMenuClick(projectsRef)} on:keyup role="button" tabindex="0">Projects</div></li>
</Menu>
<Home bind:homeRef />
<AboutMe bind:aboutMeRef {sectionNum} />
<Contact bind:contactRef />
<Projects bind:projectsRef />
