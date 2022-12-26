<script>
    import Navbar from "../components/Navbar.svelte";
</script>

<header>
    <Navbar />
</header>

<style>
    #main {
        height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>

<section id="main" class="container-fluid d-flex justify-content-center mt-5">
    <div class="d-flex flex-colum">
        <div class="container-sm">
            <h1 class="fs-1 text-primary mb-5">About me</h1>
            <p class="fs-3">My name is Sebastian Herrera. I am a self-taught developer, I am studying Visual Arts in the University of Nariño.</p>
            <p class="fs-3 text-white-50">Although I mainly work in Java, I am very familiar with languages such as Typescript and JavaScript and frameworks such as NodeJS.</p>
            <p class="fs-3">I'm looking forward to keep learning and earn experience working in different projects.</p>
        </div>
    </div>
</section>