<script lang="ts">
  import { spring } from 'svelte/motion';

  export let aboutMeRef: HTMLElement;
  export let logo: string;
  export let sectionNum: number;
  export let index: number;

  let enter = false;
  let innerWidth: number;
  let innerHeight: number;

  const coord = spring(
    { x: 0, y: 0, z: 0 },
    {
      stiffness: (((Math.random() * 100) % 3) + 1) / 100,
      damping: Math.max((((Math.random() * 100) % 25) + 1) / 100, 0.15),
    }
  );

  $: {
    if (sectionNum === 2 || enter) {
      $coord = { x: 0, y: 0, z: 0 };
    } else {
      $coord = {
        x: (innerWidth + Math.random() * innerWidth) * (index % 2 === 0 ? 1 : -1),
        y: (innerHeight + Math.random() * innerHeight) * (index % 2 === 0 ? 1 : -1),
        z: Math.random() * 4 * (index % 2 === 0 ? -1 : 1),
      };
    }
  }

  const handleScroll = () => {
    if ([3, 4].includes(sectionNum)) {
      enter = false;
      return;
    }
    if (aboutMeRef?.getBoundingClientRect().top < innerHeight / 2.2) {
      enter = true;
    } else if (aboutMeRef?.getBoundingClientRect().top >= innerHeight) {
      enter = false;
    }
  };
</script>

<svelte:window bind:innerWidth bind:innerHeight on:scroll={handleScroll} />

<div>
  <img
    src={logo}
    alt={logo}
    style="transform: translate3d({$coord.x}px, {$coord.y}px, {$coord.z}px);"
  />
</div>

<style>
  div {
    perspective: 0;
  }

  img {
    height: 64px;
    margin-right: 24px;
    margin-top: 15px;
  }

  @media (max-width: 708px) {
    img {
      height: 32px;
    }
  }
</style>
