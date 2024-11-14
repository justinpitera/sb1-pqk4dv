<script lang="ts">
  export let title: string;
  export let value: string;
  export let change: string;
  export let status: 'success' | 'warning' | 'error';

  const getStatusColor = (status: string) => {
    switch (status) {
      case 'success': return 'text-green-400';
      case 'warning': return 'text-yellow-400';
      case 'error': return 'text-red-400';
      default: return 'text-gray-400';
    }
  };
</script>

<div class="bg-gray-700 p-4 rounded-lg">
  <h3 class="text-gray-400 text-sm font-medium">{title}</h3>
  <div class="mt-2 flex justify-between items-end">
    <p class="text-2xl font-semibold">{value}</p>
    <p class={`text-sm ${getStatusColor(status)}`}>{change}</p>
  </div>
</div>