<script lang="ts">
  import { 
    LayoutDashboard, 
    FolderGit2, 
    Search, 
    Zap, 
    AlertTriangle, 
    Settings 
  } from 'lucide-svelte';


  const menuItems = [
    { label: 'Dashboard', icon: LayoutDashboard },
    { label: 'Projects', icon: FolderGit2 },
    { label: 'Static Analysis', icon: Search },
    { label: 'Dynamic Analysis', icon: Zap },
    { label: 'Issues', icon: AlertTriangle },
    { label: 'Settings', icon: Settings }
  ];

  let activeItem = 'Dashboard';
</script>

<aside class="w-64 bg-zinc-900 border-r border-zinc-800">
  <div class="p-6">
    <h1 class="text-xl font-bold text-zinc-100">Pitera Co.</h1>
  </div>
  <nav class="mt-6">
    {#each menuItems as item}
      <a
        href="/"
        class="flex items-center px-6 py-3 text-zinc-400 hover:bg-zinc-800 hover:text-zinc-100 {activeItem === item.label ? 'bg-zinc-800 text-zinc-100' : ''}"
        on:click={() => activeItem = item.label}
      >
        <svelte:component this={item.icon} class="w-5 h-5 mr-3" />
        <span>{item.label}</span>
      </a>
    {/each}
  </nav>
</aside>