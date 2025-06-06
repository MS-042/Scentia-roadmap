<script>
  import { Fa } from 'svelte-fa';
  import {
    faAsterisk, faPencil, faTasks,
    faThermometerHalf, faBuilding, faCogs
  } from '@fortawesome/free-solid-svg-icons';

  const ICONS = {
    asterisk: faAsterisk,
    pencil: faPencil,
    tasks: faTasks,
    'thermometer-half': faThermometerHalf,
    'building-o': faBuilding,
    cogs: faCogs
  };

  export let card;
</script>

<div class="timeline-box">
  <div class="box-title">
    <Fa icon={ICONS[card.icon]} class={"icon-" + card.iconColor} />
    {card.title}
  </div>

  <div class="box-content">
    {#if card.cta}
      <a class="btn btn-xs btn-default pull-right">Details</a>
    {/if}

    {#each Object.entries(card.fields) as [k,v]}
      <div class="box-item"><strong>{k}</strong>: {v}</div>
    {/each}
  </div>

  <div class="box-footer">- {card.by}</div>
</div>

<style>
  .timeline-box {
    overflow: hidden;
    border: 1px solid #17191b;
    border-radius: 15px;
    border-top-left-radius: 0;
    border-bottom-right-radius: 0;
    background: #444950;
    transition: transform .3s;
  }
  .timeline-box:hover { transform: translateY(-2px); }

  .box-title {
    padding: 5px 15px;
    border-bottom: 1px solid #17191b;
    display: flex; gap: 6px; align-items: center;
  }
  .box-content { padding: 5px 15px; background: #17191b; }
  .box-content strong { color:#666; font-style:italic; margin-right:5px; }
  .box-item { margin-bottom:5px; }
  .box-footer { padding:5px 15px; border-top:1px solid #17191b; background:#444950; text-align:right; font-style:italic; }

  /* legacy bootstrap btn override */
  :global(.btn.btn-xs.btn-default){
    font-size:.7rem;padding:.15rem .5rem;background:#e7e7e7;border:1px solid #ccc;border-radius:2px;
  }

  .icon-success{color:#5cb85c}.icon-info{color:#5bc0de}
  .icon-primary{color:#0275d8}.icon-warning{color:#f0ad4e}
  .icon-default{color:#adb5bd}
</style>
