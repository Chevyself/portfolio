<script>
    let name;
    let description;
    let links = [];
    let tecnologies = [];
    let role;
    let difficulties;
    let solutions;
    let features;
    let darker = true;

    export {
        name,
        description,
        links,
        tecnologies,
        role,
        difficulties,
        solutions,
        features,
        darker
    };
</script>
<style>
    h1,
    h2,
    h3
     {
        color: #f0b90b;
    }

    a {
        text-decoration: none;
    }
</style>
<div class="job p-5 row {darker ? "bg-dark" : "bg-gray-800"}">
    <div class="col-sm-12 col-md-6">
        <h1 class="mb-3">{name}</h1>
        {#if links !== null && links.length > 0}
            <div class="container text-center">
                <div class="row">
                    {#each links as link}
                        <div class="col">
                            {#if link.icon !== null}
                                <a href={link.href}
                                    ><i class="bi bi-{link.icon}" />
                                    {link.text}</a
                                >
                            {:else}
                                <a href={link.href}>{link.text}</a>
                            {/if}
                        </div>
                    {/each}
                </div>
            </div>
        {/if}
        <p>{description}</p>
        <hr />
        <h2>tecnologies</h2>
        <div class="container">
            <ul class="row">
                {#each tecnologies as tecnology}
                    <li class="col-sm-6">
                        <p>{tecnology}</p>
                    </li>
                {/each}
            </ul>
        </div>
    </div>
    <div class="col-sm-12 col-md-6">
        <h3>my role</h3>
        <p>{role}</p>
        <h3>difficulties</h3>
        <p>{difficulties}</p>
        <h3>solutions</h3>
        <p>{solutions}</p>
        {#if features}
            <hr />
            <h2>features</h2>
            <ul>
                {#each features as feature}
                    <li>{feature}</li>
                {/each}
            </ul>
        {/if}
    </div>
</div>
