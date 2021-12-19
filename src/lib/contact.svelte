<script lang="ts">
  import avatar from '/static/images/avatar-bkg-bw.jpg';
  import { logoUrls } from '$lib/data/imgUrls';

  export let contactRef: HTMLElement = null;
</script>

<section class="app-section" bind:this={contactRef}>
  <div class="heading-wrapper">
    <img class="avatar" src={avatar} alt="portrait" />
    <h1 class="section-heading contact-section-heading">Contact</h1>
  </div>
  <div class="contact-info-group">
    <div class="contact-item">
      <div class="contact-icon">
        <i class="fa fa-envelope" />
      </div>
      <a href="mailto:evanrmorrison@gmail.com">evanrmorrison@gmail.com</a>
    </div>
    <hr />
    <div class="contact-item">
      <div class="contact-icon">
        <i class="fa fa-mobile" />
      </div>
      <a href="tel:801-792-9290">801-792-9290</a>
    </div>
    <hr />
    <div class="contact-item">
      <div class="github-logo contact-icon">
        <img src={logoUrls.Github} alt="Github" />
      </div>
      <a href="https://github.com/EvanMorrison">EvanMorrison</a>
    </div>
    <hr />
    <div class="contact-item">
      <div class="contact-icon">
        <i class="fa fa-file-alt" />
      </div>
      <a
        href="https://drive.google.com/file/d/0B8qa-UZelBhOQXUzb0h4MDg1Wmc/view?usp=sharing"
        target="_blank">view/download resume</a
      >
    </div>
  </div>
</section>

<style>
  .heading-wrapper {
    position: relative;
    margin-bottom: 30px;
  }

  .avatar {
    border-radius: 50%;
    width: 150px;
    z-index: -1;
    position: absolute;
    transform: translate(-115px, -30px);
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
    margin-top: 30px;
    align-items: left;
    width: 90%;
    max-width: 400px;
  }

  .contact-info-group .contact-item {
    padding: 10px 0;
    display: flex;
  }

  .contact-info-group .contact-icon {
    flex-basis: 60px;
    font-size: 26px;
    text-align: center;
    padding-right: 20px;
  }

  .contact-info-group .github-logo img {
    width: 30px;
    height: 30px;
  }

  .contact-info-group a {
    color: #f58;
  }

  @media (min-width: 650px) {
    .contact-info-group a {
      font-size: 20px;
    }
  }
</style>
