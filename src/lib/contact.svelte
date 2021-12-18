<script lang="ts">
  export let contactRef: HTMLElement;

  const url = 'https://i.imgur.com/wmK5ZW9.jpg';
</script>

<section class="app-section" bind:this={contactRef}>
  <div class="heading-wrapper">
    <img class="avatar" src={url} alt="portrait" />
    <h1 class="section-heading contact-section-heading">Contact</h1>
  </div>
  <div class="contact-info-group">
    <p>
      <a href="mailto:evanrmorrison@gmail.com">evanrmorrison@gmail.com</a>
    </p>
    <p>
      <a href="tel:801-792-9290">801-792-9290</a>
    </p>
    <p>
      <img
        src=""
        alt="Github"
        style="width: 30; height: 30; margin-right: 25; position: relative; top: 10"
      />
      <a href="https://github.com/EvanMorrison">EvanMorrison</a>
    </p>
    <p>
      <a
        href="https://drive.google.com/file/d/0B8qa-UZelBhOQXUzb0h4MDg1Wmc/view?usp=sharing"
        target="_blank">view/download resume</a
      >
    </p>
  </div>
</section>

<style>
  .heading-wrapper {
    position: relative;
    margin-bottom: 30px;
  }

  .avatar {
    border-radius: 50%;
    width: 180px;
    z-index: -1;
    position: absolute;
    transform: translate(-125px, -50px);
    box-shadow: 2px 1px 5px rgba(0, 0, 0, 1);
  }

  .contact-section-heading {
    z-index: 10;
    color: #000;
    background: #fff;
    padding: 5px;
    border-radius: 40px;
    font-weight: 100;
  }

  .contact-info-group {
    align-items: left;
    width: 90%;
    max-width: 400px;
  }

  .contact-info-group a {
    color: #f58;
  }

  @media (min-width: 650px) {
    .contact-info-group a {
      font-size: 20px;
    }
  }

  p {
    margin: 20px 0 20px 0px;
  }
</style>
