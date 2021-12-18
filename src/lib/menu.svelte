<script lang="ts">
  export let onDark = false;
  export let sectionNum = 1;

  let open = true;

  const handleClickMenu = () => {
    open = !open;
  };
</script>

<div
  class="menu-wrapper"
  class:open
  style={`
    --background: ${onDark ? 'rgba(0, 0, 0, 0.3)' : 'rgba(250, 250, 250, 0.3)'};
    --color: ${onDark ? 'rgba(240, 240, 240, 0.8)' : 'rgba(50, 50, 50, 0.8)'};
    --shadow: ${onDark ? 'rgba(255, 255, 255, 0.5)' : 'rgba(0, 0, 0, 0.5)'};
    --section-num: '${sectionNum}';
    --active-menu-section-background: ${
      sectionNum % 2 === 0 ? 'rgba(100, 100, 100, 0.5)' : 'rgba(200, 200, 200, 0.5)'
    }`}
>
  <button class="open-close-button" class:open on:click={handleClickMenu}>
    <div class="open-close-arrow" class:open />
  </button>
  <ul class:open>
    <slot />
  </ul>
</div>

<style>
  .menu-wrapper {
    background-color: var(--background);
    border-top-right-radius: 3px;
    border-bottom-right-radius: 3px;
    position: fixed;
    top: 15px;
    z-index: 10;
    display: flex;
    box-shadow: 1px 1px 12px -4px var(--shadow);
    transform: translateX(-270px);
    transition: transform 0.3s ease, background-color 0.3s ease;
    cursor: pointer;
    overflow: hidden;
  }

  .menu-wrapper.open {
    transform: translateX(0);
  }

  .open-close-button {
    border-color: transparent;
    background-color: var(--background);
    position: relative;
    padding: 12px 14px 12px 8px;
    transform: translateX(270px);
    transition: transform 0.3s ease, background-color 0.3s ease;
  }

  .open-close-button.open {
    transform: translateX(0);
  }

  .open-close-arrow {
    border: 6px solid transparent;
    border-right: 6px solid var(--color);
    transition: all 0.3s ease;
    transform-origin: 9px center;
    transform: rotate(180deg);
  }

  .open-close-arrow.open {
    transform-origin: 9px center;
    transform: rotate(0);
  }

  ul {
    margin: 0;
    padding: 0;
    position: relative;
    border-left: 1px groove var(--shadow);
    display: flex;
    list-style: none;
    transform: translateX(-300px);
    transition: transform 0.3s ease;
  }

  ul.open {
    transform: translateX(0);
  }

  ul :global(li) {
    margin: 0;
    color: var(--color);
    padding: 12px;
    user-select: none;
    cursor: pointer;
    font-size: 1rem;
    transition: color 0.3s ease;
  }

  ul :global(li:hover) {
    background: rgba(150, 150, 150, 0.5);
  }

  ul :global(li.active) {
    background: var(--active-menu-section-background);
  }
</style>
