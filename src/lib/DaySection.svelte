<script>
  export let day;
  import Card from './Card.svelte';
  const [yyyy, mm, dd] = day.date.split('-');
</script>

<section class="timeline-section">
  <div class="timeline-date">{dd}, {day.label}</div>

  {#each day.cards as card, i (i)}
    <div class="row">
      <div class="col-sm-4">
        <Card {card} />
      </div>
    </div>
  {/each}
</section>

<style>
  .timeline-section {
    position: relative;
    padding-left: 35px;
    margin-bottom: 30px;
  }
  .timeline-section::before {
    content: '';
    position: absolute;
    top: 12px;
    left: 20px;
    width: 30px;
    height: 1px;
    background: #444950;
  }
  .timeline-section::after {
    content: '';
    position: absolute;
    top: 7px;
    left: 11px;
    width: 10px;
    height: 10px;
    border: 1px solid #17191b;
    border-radius: 50%;
    background: linear-gradient(#8a9196, #7a8288 60%, #70787d);
  }
  .timeline-date {
    display: inline-block;
    margin-bottom: 15px;
    padding: 2px 15px;
    color: #fff;
    background: linear-gradient(#74cae3, #5bc0de 60%, #4ab9db);
    border: 1px solid #17191b;
    border-radius: 20px;
    text-shadow: 1px 1px 1px rgba(0,0,0,0.3);
  }
</style>
