<script>
  export let monthName;
  export let monthObj;
  import DaySection from './DaySection.svelte';
</script>

<div class="timeline-month">
  {monthName}
  <span>{monthObj.entries} Entries</span>
</div>

{#each monthObj.days as day}
  <DaySection {day} />
{/each}

<style>
  .timeline-month {
    position: relative;
    padding: 4px 15px 4px 35px;
    margin-bottom: 30px;
    display: inline-block;
    background: #444950;
    border: 1px solid #17191b;
    border-radius: 40px;
  }
  .timeline-month span {
    position: absolute;
    top: -1px;
    left: calc(100% - 10px);
    white-space: nowrap;
    padding: 4px 10px 4px 20px;
    background: #111;
    border-radius: 0 40px 40px 0;
    border: 1px solid #000;
  }
  .timeline-month::before {
    content: '';
    position: absolute;
    left: 5px;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    border: 1px solid #17191b;
    background: linear-gradient(#8a9196, #7a8288 60%, #70787d);
  }
</style>
