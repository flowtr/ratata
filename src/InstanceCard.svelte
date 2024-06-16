<script lang="ts">
    export let name = "Development";
    export let tags = ["RUNNING", "CONTAINER"];
    export let description = "Dye Ratata development D-VPS";
    export let cpu = "20%";
    export let memory = "151mb";
    export let disk = "1.2gb";
</script>

<div
    class="bg-zinc-900/30 hover:bg-zinc-900 p-4 rounded-lg flex items-center space-x-4 max-h-24 cursor-pointer"
>
    <div class="h-4 w-4 text-[#58a6ff]">
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
        >
            <path
                d="M20 16V7a2 2 0 0 0-2-2H6a2 2 0 0 0-2 2v9m16 0H4m16 0 1.28 2.55a1 1 0 0 1-.9 1.45H3.62a1 1 0 0 1-.9-1.45L4 16"
            ></path>
        </svg>
    </div>
    <div class="flex flex-col">
        <div class="flex items-center space-x-2">
            <h2 class="text-white font-semibold">{name}</h2>
            {#each tags as tag}
                <div
                    class="text-xs text-white rounded-full px-2 py-1 inline-block {tag ===
                    'RUNNING'
                        ? 'bg-green-500'
                        : 'bg-blue-500'}"
                >
                    {tag}
                </div>
            {/each}
        </div>
        <p class="text-zinc-400 text-sm">{description}</p>
    </div>
    <div class="hidden md:flex items-center space-x-4">
        <div class="flex items-center">
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
                class="h-5 w-5 mr-2 text-green-500"
            >
                <rect x="4" y="4" width="16" height="16" rx="2"></rect>
                <rect x="9" y="9" width="6" height="6"></rect>
                <path d="M15 2v2"></path>
                <path d="M15 20v2"></path>
                <path d="M2 15h2"></path>
                <path d="M2 9h2"></path>
                <path d="M20 15h2"></path>
                <path d="M20 9h2"></path>
                <path d="M9 2v2"></path>
                <path d="M9 20v2"></path>
            </svg>
            <span class="text-zinc-100">
                <p class="text-zinc-400 text-xs font-bold">CPU</p>
                {cpu}
            </span>
        </div>
        <div class="flex items-center">
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
                class="h-5 w-5 mr-2 text-yellow-500"
            >
                <path d="M6 19v-3"></path>
                <path d="M10 19v-3"></path>
                <path d="M14 19v-3"></path>
                <path d="M18 19v-3"></path>
                <path d="M8 11V9"></path>
                <path d="M16 11V9"></path>
                <path d="M12 11V9"></path>
                <path d="M2 15h20"></path>
                <path
                    d="M2 7a2 2 0 0 1 2-2h16a2 2 0 0 1 2 2v1.1a2 2 0 0 0 0 3.837V17a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2v-5.1a2 2 0 0 0 0-3.837Z"
                ></path>
            </svg>
            <span class="text-zinc-100">
                <p class="text-zinc-400 text-xs font-bold">Memory</p>
                {memory}
            </span>
        </div>
        <div class="flex items-center">
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
                class="h-5 w-5 mr-2 text-red-500"
            >
                <line x1="22" x2="2" y1="12" y2="12"></line>
                <path
                    d="M5.45 5.11 2 12v6a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2v-6l-3.45-6.89A2 2 0 0 0 16.76 4H7.24a2 2 0 0 0-1.79 1.11z"
                ></path>
                <line x1="6" x2="6.01" y1="16" y2="16"></line>
                <line x1="10" x2="10.01" y1="16" y2="16"></line>
            </svg>
            <span class="text-zinc-100">
                <p class="text-zinc-400 text-xs font-bold">Disk</p>
                {disk}
            </span>
        </div>
        <button
            class="inline-flex
					md:hidden
					items-center justify-center rounded-md text-sm font-medium ring-offset-background focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 border hover:text-accent-foreground h-10 px-4 py-2 bg-blue-500 border-blue-500 hover:bg-blue-600 hover:border-blue-600 transition-colors duration-200 ease-in-out"
        >
            Manage
        </button>
    </div>
</div>
