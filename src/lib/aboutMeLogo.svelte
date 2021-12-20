<script lang="ts">
  import { spring } from 'svelte/motion';

  export let aboutMeRef: HTMLElement;
  export let logo: string;
  export let sectionNum: number;

  let enter = false;
  let innerWidth: number;
  let innerHeight: number;

  const calcStiffness = () => (((Math.random() * 100) % 20) + 81) / 10000;
  const damping = 0.14;

  const coord = spring(
    { x: 0, y: 0, z: 0 },
    {
      stiffness: calcStiffness(),
      damping,
    }
  );

  $: {
    if (sectionNum === 2 || enter) {
      coord.stiffness = calcStiffness();
      $coord = { x: 0, y: 0, z: 0 };
    } else {
      $coord = {
        x: Math.random() * innerWidth * (Math.round(Math.random()) ? 1 : -1),
        y: Math.random() * innerHeight * (Math.round(Math.random()) ? 1 : -1),
        z: Math.random() * 4,
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
    height: 50px;
    margin-right: 24px;
    margin-top: 15px;
  }

  @media (max-width: 708px) {
    img {
      height: 32px;
    }
  }
</style>
