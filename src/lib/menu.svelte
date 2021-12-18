<script>
  let onDark = false;
  let open = true;

  const handleClickMenu = () => {
    open = !open;
  };
</script>

<div
  class="menu-wrapper"
  class:open
  style="
    --background: {onDark ? 'rgba(0, 0, 0, 0.3)' : 'rgba(250, 250, 250, 0.3)'}; 
    --color: {onDark ? 'rbga(240, 240, 240, 0.8)' : 'rgba(50, 50, 50, 0.8)'}; 
    --shadow: {onDark ? 'rgba(255, 255, 255, 0.5)' : 'rgba(0, 0, 0, 0.5)'}
  "
>
  <div class="open-close-button" class:open on:click={handleClickMenu}>
    <div class="open-close-arrow" class:open />
  </div>
  <ul class:open>
    <slot />
  </ul>
</div>

<style>
  .menu-wrapper {
    background: var(--background);
    border-radius: 3px;
    position: fixed;
    top: 15px;
    z-index: 10;
    display: flex;
    box-shadow: 1px 1px 12px -4px var(--shadow);
    transform: translateX(-280px);
    transition: transform 0.3s ease;
    cursor: pointer;
  }

  .menu-wrapper.open {
    transform: translateX(0);
  }

  .open-close-button {
    display: inline-block;
    position: relative;
    padding: 12px 14px 12px 8px;
    transform: translateX(280px);
    transition: transform 0.3s ease;
  }

  .open-close-button.open {
    transform: translateX(0);
  }

  .open-close-arrow {
    display: inline-block;
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
    display: inline-block;
    list-style: none;
    transform: translateX(-300px);
    transition: transform 0.3s ease;
  }

  ul.open {
    transform: translateX(0);
  }

  ul :global(li) {
    margin: 0;
    display: inline-block;
    color: var(--color);
    padding: 12px;
    user-select: none;
    cursor: pointer;
    font-size: 1rem;
  }

  ul :global(li:hover) {
    background: rgba(150, 150, 150, 0.5);
  }

  ul :global(li:nth-of-type(var(--section-number))) {
    background: var(--section-list-item-background);
  }
</style>
