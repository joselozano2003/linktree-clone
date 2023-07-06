<script lang="ts">
   import { user, userData } from "$lib/firebase";
    import "../app.css";


   $user;
   $userData; 
</script>

<svelte:head>
	<title>User Login</title>
</svelte:head>
<div class="min-h-screen flex flex-col">
    <slot />
</div>
