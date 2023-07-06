<script lang="ts">
    import type { PageData } from "./$types";
    import { page } from '$app/stores';
    import { enhance } from "$app/forms";
	import { db, userData, user } from "$lib/firebase";

  
    export let data: PageData;
  
</script>
  
<svelte:head>
	<title>Edit Bio</title>
</svelte:head>

<main class="max-w-lg prose text-center mx-auto my-6">
  
    <p>Current Bio: <span class="text-info">{data.bio}</span></p>
  
    <p>Status Code: {$page.status}</p>
    <p class="text-error">{$page.form?.problem ?? ''}</p>
  
    <form method="POST" use:enhance>
		<div class="form-control">
			<label for="bio" class="label justify-center">
			<span class="label-text">Your bio</span>
			</label>
			<textarea
			name="bio"
			class="textarea textarea-bordered textarea-accent"
			value={data.bio}
			/>
		</div>
		<button class="btn btn-primary my-5">Update Bio</button>
		{#if $userData?.username}
			<a class="btn btn-secondary" href="/{$userData.username}/edit">Go back</a>
		{/if}
    </form>
</main>
  