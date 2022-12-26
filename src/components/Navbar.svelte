<script>
  import { onMount } from "svelte";

  let page = "";
  
  onMount(() => {
    // Smoothly scroll to anchor links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();

        document.querySelector(this.getAttribute('href')).scrollIntoView({
          behavior: 'smooth'
        });
      });
    });
    page = window.location.href;
  });
</script>

<!-- Make the navbar stick to the top -->

<nav class="navbar fixed-top navbar-expand-lg bg-secondary text-dark nav-hover">
  <div class="container-fluid ms-5 me-5">
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0 container-fluid d-flex justify-content-center">
        <li class="nav-item">
          <a class="nav-link" href="{page === "/" ? "#landing" : "./"}">Home</a>
        </li>
        <li class="nav-item">
          <a id="work-button" class="nav-link" href="{page === "/" ? "#work" : "./#work"}">Work</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="./about">About</a>  
        </li>
        <li class="nav-item">
          <a class="nav-link" href="./contact">Contact</a>
        </li>
      </ul>
    </div>
  </div>
</nav>