<script>
  import { slide } from 'svelte/transition';
  export let project;
  export let isActive;
  export let toggle;
  export let index;
</script>

<style>
  .accordion-header {
    width: 100%;
    cursor: pointer;
    padding: 8px 0;
    display: flex;
    justify-content: space-between;
  }

  .accordion-header:hover span {
   color: #9e9e9e;
  }

  .accordion-content {
    overflow: hidden;
    padding: 0 1em;
  }

  .accordion-item {
    margin-bottom: 10px;
    border-bottom: 1px solid;
  }

  button {
    background-color: inherit;
    border: none;
  }

  img {
    max-width: 100%;
  }
</style>


<div class="accordion-item">
  <button class="accordion-header" on:click={() => toggle(index)}>
    <span>{project.name}</span>
    <span>{project.year}</span>
  </button>
  {#if isActive}
    <div class="accordion-content" transition:slide>
      <img src={project.mediaSrc} alt={project.mediaAlt}>
      <p>{project.text}</p>
      <div>
        <p>
          <a href={project.githubLink} target="_blank" rel="noopener noreferrer">Github</a>
        </p>
        <p>
          <a href={project.liveSiteLink} target="_blank" rel="noopener noreferrer">Live Site</a>
        </p>
      </div>
    </div>
  {/if}
</div>