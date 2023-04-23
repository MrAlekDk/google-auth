<script>
    import { onMount } from "svelte";
    let user;

    onMount(() => {
            google.accounts.id.initialize({
            client_id: import.meta.env.VITE_CLIENT_ID,
            callback: handleCredentialResponse,
            });

            google.accounts.id.renderButton(
                document.getElementById("google-login"),
                { theme: "outline", size: "large", type: "standard" } // customization attributes
            );

            google.accounts.id.prompt(); // also display the One Tap dialog
            
  });


  function handleCredentialResponse(gg){
    let response = gg.credential
    user = response;
    document.getElementById("google-login").hidden = true;
  }

  function handleSignOut() {
    google.accounts.id.disableAutoSelect();
    user = null;
    document.getElementById("google-login").hidden = false;
  }
   

</script>
<h1>Google external login</h1>

{#if user}
<div class="logged-in-box">
    <h2>Logged in</h2>
    <p>You are currently logged in.</p>
    <button on:click={handleSignOut}>Logout</button>
</div>
{:else}
<div class="not-logged-in-box">
    <h2>Not logged in</h2>
    <p>You are currently not logged in.</p>
</div>
{/if}
<div id="google-login" />

<style>

    :global(body){
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background-image: url("yoshi mlem.png");
        background-repeat: no-repeat;
        background-position: center;
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