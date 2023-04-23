<script>

    let loggedIn = false;



</script>
<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>


{#if loggedIn}
<div class="logged-in-box">

</div>
{:else}
<div class="not-logged-in-box">
    <h2>Not logged in</h2>
    <p>You are currently not logged in.</p>
    <input>
    <button>Login with google</button>
</div>
{/if}

<style>

    :global(body){
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    h1{
        font-weight: bolder;
        font-size: 30px;
        text-align: center;
    }

    .not-logged-in-box{
        display: flex;
        flex-direction: column;
        align-items: center;
    }



</style>