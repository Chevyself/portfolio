<script>
  import Navbar from "../components/Navbar.svelte";
  import Work from "../components/Work.svelte";
</script>

<svelte:head>
  <title>Backend Developer - Chevy</title>
</svelte:head>

<header>
  <Navbar />
</header>
<section id="landing" class="d-flex justify-content-center">
  <div class="container">
    <p class="lead">Hello! I'm</p>
    <h1 class="display-1 fw-bold ms-n1">Chevy</h1>
    <h1 class="display-3">Backend developer</h1>
    <p>
      I specialize in Minecraft plugins and Discord bots development. Let's get
      started with your next project:
    </p>
    <a href="#work" type="button" class="btn btn-primary btn-lg px-4 gap-3"
      >My Work</a
    >
  </div>
</section>
<section id="work" class="container-fluid">
  <Work />
</section>
<section id="ready" class="dflex justify-content-center p-5">
  <div class="container">
    <h1 class="display-4">Ready to get started?</h1>
    <p class="lead">
      I'm always looking for new projects to work on. Let's get us started:
    </p>
    <a href="./contact" type="button" class="btn btn-primary btn-lg px-4 gap-3"
      >Contact Me</a
    >
  </div>
</section>

<style>
  #landing {
    animation: fadeInUp 1.7s;
  }

  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translate3d(0, 40px, 0);
    }

    to {
      opacity: 1;
      transform: none;
    }
  }

  #landing {
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  #ready {
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
