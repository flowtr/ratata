<script lang="ts">
  import { onMount } from "svelte";
  import InstanceListPage from "./pages/InstanceListPage.svelte";
  import Sidebar from "./Sidebar.svelte";
  import { HomeIcon, ServerIcon, ShuffleIcon } from "lucide-svelte";

  const pages = [
    { name: "Dashboard", icon: HomeIcon, href: "dashboard" },
    {
      name: "Instances",
      component: InstanceListPage,
      icon: ServerIcon,
      href: "instances",
    },
    { name: "Reverse Proxies", icon: ShuffleIcon, href: "reverse-proxies" },
  ];

  let currentPage: string = "dashboard";

  onMount(() => {
    if (location.hash === "") {
      location.hash = currentPage;
    }

    currentPage = location.hash.slice(1);
  });

  const routeChange = () => {
    currentPage = location.hash.slice(1);
  };
</script>

<svelte:window on:hashchange={routeChange} />

<div class="flex flex-col md:flex-row h-screen bg-zinc-950">
  <Sidebar items={pages} activeItem={currentPage} />
  <main class="flex-1 p-4 md:p-6 overflow-auto">
    {#if pages.find((page) => page.href === currentPage)?.component !== undefined}
      <svelte:component
        this={pages.find((page) => page.href === currentPage)?.component}
      />
    {/if}
  </main>
</div>
