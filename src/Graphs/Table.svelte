<script lang="ts">
import type { QueryMetrics,QueryData } from '../types';

export let metric:QueryData;

const queryMetrics:QueryMetrics[] = metric.queryMetrics

</script>

<div class="scrollbar-hide overflow-y-auto">
  <div class="overflow-x-auto ">
    <table class="table">
      <!-- head -->
      <thead>
        <tr>
          <th>#</th>
          <th>Planning Time</th>
          <th>Execution Time</th>
          <th>Total Time</th>
          <th>Shared Hit Blocks</th>
          <th>Shared Read Blocks</th>
        </tr>
      </thead>
      <tbody>
        <!-- iterate through queryMetrics array and pass values into the table -->
        {#each queryMetrics as metric, i}
          <tr>

            <th>{i+1}</th>
            <td>{metric.planningTime}</td>
            <td>{metric.executionTime}</td>
            <td>{metric.totalTime}</td>
            <td>{metric.sharedHitBlocks}</td>
            <td>{metric.sharedReadBlocks}</td>
          </tr>
          {/each}
      </tbody>
    </table>
  </div>
</div>