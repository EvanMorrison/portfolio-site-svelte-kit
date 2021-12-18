<script>
  import '../app.css';
  import Menu from '$lib/menu.svelte';
  import Home from '$lib/home.svelte';
  import AboutMe from '$lib/aboutMe.svelte';
  import Contact from '$lib/contact.svelte';
  import Projects from '$lib/projects.svelte';
</script>

<Menu>
  <li>Top</li>
  <li>About</li>
  <li>Contact</li>
  <li>Projects</li>
</Menu>
<Home />
<AboutMe />
<Contact />
<Projects />
