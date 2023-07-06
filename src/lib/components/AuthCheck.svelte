<script lang="ts">
    import { user } from "$lib/firebase";
</script>
  
{#if $user}
	<slot />
{:else}
	<p class="text-error my-10">You are not logged in</p>
	<a class="btn btn-primary" href="/login">Sign in</a>
{/if}
  