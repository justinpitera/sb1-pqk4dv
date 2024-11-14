<script lang="ts">
  import Sidebar from './components/Sidebar.svelte';
  import Dashboard from './components/Dashboard.svelte';
  import Header from './components/Header.svelte';
</script>

<div class="flex h-screen bg-background">
  <Sidebar />
  <div class="flex-1 flex flex-col overflow-hidden">
    <Header />
    <main class="flex-1 overflow-x-hidden overflow-y-auto">
      <Dashboard />
    </main>
  </div>
</div>

<style>
  :global(body) {
    margin: 0;
    font-family: system-ui, sans-serif;
  }
</style>