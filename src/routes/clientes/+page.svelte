<script lang="ts">
  import type { UserPlaceholderResponse } from 'src/types/UserPlaceholderReponse';
  import { onMount } from 'svelte';

  let data: UserPlaceholderResponse[] = [];

  onMount(async () => {
    // get fake data
    const resp = await fetch('https://jsonplaceholder.typicode.com/users');
    data = await resp.json();
  });
</script>

<h1 class="text-5xl m-4">Clientes</h1>

<!-- Components of tailwind of cards with info -->
<section class="grid grid-cols-3 gap-8 mx-4">
  {#each data as item, idx}
    <article class="overflow-hidden rounded-lg shadow-lg">
      <a href="#">
        <img
          alt="Placeholder"
          class="block h-auto w-full "
          width="200"
          height="200"
          src={`https://picsum.photos/300/30${idx}`}
        />
      </a>
      <header
        class="flex items-center justify-between leading-tight p-2 md:p-4"
      >
        <h1 class="text-lg">
          <a class="no-underline hover:underline text-black" href="#">
            {item.name}
          </a>
        </h1>
        <p class="text-grey-darker text-sm">{item.email}</p>
      </header>

      <footer class="flex items-center justify-between leading-none p-2 md:p-4">
        <a
          class="flex items-center no-underline hover:underline text-black"
          href="#"
        >
          <p class="ml-2 text-sm">{item.phone}</p>
        </a>
      </footer>
    </article>
  {/each}
</section>

<style>
</style>
