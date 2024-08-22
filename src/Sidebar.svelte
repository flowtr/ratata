<script lang="ts">
  import { ShuffleIcon, HomeIcon, ServerIcon } from "lucide-svelte";

  export let activeItem: string;

  export let items: {
    name: string;
    component?: unknown;
    icon: unknown;
    href: string;
  }[] = [];
</script>

<aside
  class="md:hidden bg-zinc-900/30 border-b border-zinc-800 p-5 flex justify-between items-center"
>
  <div class="flex items-center space-x-2">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      width="24"
      height="24"
      viewBox="0 0 24 24"
      fill="none"
      stroke="currentColor"
      stroke-width="2"
      stroke-linecap="round"
      stroke-linejoin="round"
      class="h-8 w-8 text-white"
    >
      <path d="M17.5 19H9a7 7 0 1 1 6.71-9h1.79a4.5 4.5 0 1 1 0 9Z"></path>
    </svg>
    <span class="text-white font-bold">Dye Cloud</span>
  </div>
  <svg
    xmlns="http://www.w3.org/2000/svg"
    width="24"
    height="24"
    viewBox="0 0 24 24"
    fill="none"
    stroke="currentColor"
    stroke-width="2"
    stroke-linecap="round"
    stroke-linejoin="round"
    class="h-5 w-5 text-white"
  >
    <line x1="4" x2="20" y1="12" y2="12"></line>
    <line x1="4" x2="20" y1="6" y2="6"></line>
    <line x1="4" x2="20" y1="18" y2="18"></line>
  </svg>
</aside>
<aside
  class="hidden w-60 bg-zinc-900/30 border-r border-zinc-800 p-5 md:flex flex-col justify-between"
>
  <div>
    <div class="flex items-center space-x-2 mb-6">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
        stroke="currentColor"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
        class="h-8 w-8 text-sky-300"
      >
        <path d="M17.5 19H9a7 7 0 1 1 6.71-9h1.79a4.5 4.5 0 1 1 0 9Z"></path>
      </svg>
      <span class="text-sky-300 font-black">
        Dye Cloud
        <p class="text-zinc-400 font-bold text-xs">Powered by Ratata</p>
      </span>
    </div>
    <nav class="text-white">
      <ul>
        {#each items as item}
          <li class="mb-2">
            <a
              class="flex items-center space-x-2 p-2 rounded bg-zinc-900 relative"
              href="#{item.href}"
              rel="ugc"
              on:click={() => (activeItem = item.href)}
            >
              {#if activeItem === item.href}
                <div
                  class="absolute bg-sky-300 px-[2.5px] py-3 rounded-full -left-0.5"
                ></div>
              {/if}

              <svelte:component this={item.icon} class="h-5 w-5" />

              <span>{item.name}</span>
            </a>
          </li>
        {/each}
      </ul>
    </nav>
  </div>
</aside>
