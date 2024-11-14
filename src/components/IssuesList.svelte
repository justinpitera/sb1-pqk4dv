<script lang="ts">
  const issues = [
    {
      id: 1,
      title: 'High cyclomatic complexity in UserService',
      type: 'Code Smell',
      severity: 'Major',
      file: 'src/services/UserService.ts',
      line: 127
    },
    {
      id: 2,
      title: 'Memory leak in DataProcessor',
      type: 'Bug',
      severity: 'Critical',
      file: 'src/utils/DataProcessor.ts',
      line: 45
    },
    {
      id: 3,
      title: 'Unused import statement',
      type: 'Code Smell',
      severity: 'Minor',
      file: 'src/components/Chart.tsx',
      line: 12
    }
  ];

  const getSeverityColor = (severity: string) => {
    switch (severity.toLowerCase()) {
      case 'critical': return 'bg-red-500 text-zinc-100';
      case 'major': return 'bg-orange-500 text-zinc-100';
      case 'minor': return 'bg-yellow-500 text-zinc-900';
      default: return 'bg-zinc-500 text-zinc-100';
    }
  };
</script>

<div class="overflow-x-auto">
  <table class="min-w-full">
    <thead>
      <tr class="text-left text-zinc-400 border-b border-zinc-200 dark:border-zinc-700">
        <th class="px-6 py-3">Issue</th>
        <th class="px-6 py-3">Type</th>
        <th class="px-6 py-3">Severity</th>
        <th class="px-6 py-3">Location</th>
      </tr>
    </thead>
    <tbody class="divide-y divide-zinc-200 dark:divide-zinc-700">
      {#each issues as issue}
        <tr class="hover:bg-zinc-50 dark:hover:bg-zinc-800">
          <td class="px-6 py-4">{issue.title}</td>
          <td class="px-6 py-4">{issue.type}</td>
          <td class="px-6 py-4">
            <span class={`px-2 py-1 rounded-full text-xs ${getSeverityColor(issue.severity)}`}>
              {issue.severity}
            </span>
          </td>
          <td class="px-6 py-4">
            <span class="text-zinc-500 dark:text-zinc-400">{issue.file}:{issue.line}</span>
          </td>
        </tr>
      {/each}
    </tbody>
  </table>
</div>