<script lang="ts">
  import { Search, Bell } from 'lucide-svelte';
  let searchQuery = '';
</script>

<header class="border-b">
  <div class="flex h-16 items-center px-4">
    <div class="flex flex-1 items-center space-x-4">
      <div class="relative">
        <Search class="absolute left-2.5 top-2.5 h-4 w-4 text-muted-foreground" />
        <input
          type="text"
          bind:value={searchQuery}
          placeholder="Search..."
          class="pl-8 h-9 w-[200px] lg:w-[300px] rounded-md border border-input bg-background px-3 py-1 text-sm shadow-sm transition-colors placeholder:text-muted-foreground focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-ring"
        />
      </div>
    </div>
    <div class="flex items-center space-x-4">
      <button class="text-muted-foreground hover:text-foreground transition-colors">
        <Bell class="h-5 w-5" />
      </button>
      <div class="h-8 w-8 rounded-full bg-primary flex items-center justify-center text-primary-foreground">
        <span class="text-sm font-medium">JD</span>
      </div>
    </div>
  </div>
</header>