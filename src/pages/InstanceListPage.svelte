<script>
  import { PlusIcon } from "lucide-svelte";
  import InstanceCard from "../InstanceCard.svelte";
</script>

<div class="flex justify-between items-center mb-4">
  <h1 class="text-lg md:text-2xl text-white font-semibold">Instances</h1>
  <button
    class="text-sm font-medium ring-offset-background transition-colors
    focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring
    focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50
    px-4 py-2 fixed bottom-4 right-4 bg-[#238636] text-white hover:bg-emerald-600
    rounded-full h-12 w-12 flex items-center justify-center
    "
  >
    <PlusIcon />
  </button>
</div>
<div class="w-full h-full grid grid-cols-1 gap-4">
  <InstanceCard />
</div>
