<script>
  export let data;
  import MonthGroup from './MonthGroup.svelte';
</script>

<div class="timeline">
  {#each Object.entries(data) as [monthName, monthObj]}
    <MonthGroup {monthName} {monthObj} />
  {/each}
</div>

<style>
  .timeline {
    margin-top: 20px;
    position: relative;
  }

  .timeline::before {
    content: '';
    position: absolute;
    left: 14px;
    top: 5px;
    width: 4px;
    height: calc(100% + 50px);
    border-radius: 4px;
    background: linear-gradient(
      to right,
      #8a9196 0%,
      #7a8288 60%,
      #62696d 100%
    );
  }
</style>
