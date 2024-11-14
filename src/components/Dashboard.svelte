<script lang="ts">
  import { Card, CardContent, CardHeader, CardTitle } from "./ui/card";
  import CodeQualityChart from './CodeQualityChart.svelte';
  import IssuesList from './IssuesList.svelte';
  import PerformanceWidget from './PerformanceWidget.svelte';
  import { TrendingUp, Bug, Clock, Shield } from 'lucide-svelte';

  const metrics = [
    { title: 'Code Smells', value: '127', change: '-12%', status: 'success', icon: TrendingUp },
    { title: 'Bugs', value: '23', change: '+5%', status: 'warning', icon: Bug },
    { title: 'Technical Debt', value: '4.2d', change: '-2%', status: 'success', icon: Clock },
    { title: 'Coverage', value: '87%', change: '+3%', status: 'success', icon: Shield },
  ];
</script>

<div class="container p-6 space-y-6">
  <h1 class="text-3xl font-bold tracking-tight">Dashboard</h1>
  
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
    {#each metrics as metric}
      <Card>
        <CardHeader class="flex flex-row items-center justify-between space-y-0 pb-2">
          <CardTitle class="text-sm font-medium">
            {metric.title}
          </CardTitle>
          <svelte:component this={metric.icon} class="h-4 w-4 text-muted-foreground" />
        </CardHeader>
        <CardContent>
          <div class="text-2xl font-bold">{metric.value}</div>
          <p class="text-xs text-muted-foreground">
            <span class={metric.status === 'success' ? 'text-green-500' : 'text-yellow-500'}>
              {metric.change}
            </span>
            from last month
          </p>
        </CardContent>
      </Card>
    {/each}
  </div>

  <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
    <Card>
      <CardHeader>
        <CardTitle>Code Quality Trends</CardTitle>
      </CardHeader>
      <CardContent>
        <CodeQualityChart />
      </CardContent>
    </Card>
    <Card>
      <CardHeader>
        <CardTitle>Performance Metrics</CardTitle>
      </CardHeader>
      <CardContent>
        <PerformanceWidget />
      </CardContent>
    </Card>
  </div>

  <Card>
    <CardHeader>
      <CardTitle>Recent Issues</CardTitle>
    </CardHeader>
    <CardContent>
      <IssuesList />
    </CardContent>
  </Card>
</div>