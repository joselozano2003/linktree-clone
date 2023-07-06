<script lang="ts">
    import UserLink from "$lib/components/UserLink.svelte";
    import type { PageData } from "./$types";
    
    export let data: PageData;
</script>
  
<svelte:head>
    <title>@{data.username} Links</title>
    <meta name="description" content={data.bio} />
</svelte:head>
  
  
<main class="prose text-center mx-auto mt-8">

	<h1 class="text-3xl lg:text-3xl text-purple-500">
      	@{data.username}
    </h1>
  
    <img
      	src={data.photoURL ?? "/user.png"}
      	alt="photoURL"
      	width="256"
      	class="mx-auto mt-10"
    />
  
    <p class="text-3xl my-8 text-orange-500">{data.bio ?? "no bio yet..."}</p>
    <ul class="list-none px-2 m-0">
        {#each data.links as item}
          	<li class="my-2">
            	<UserLink {...item} />
          	</li>
        {/each}
    </ul>
  
</main>
  