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
    padding: 0;
    transform: translateZ(0); /* forces hardware acceleration */
    transition: transform 0.3s ease, opacity 0.3s ease;
  }

  .accordion-item {
    margin-bottom: 10px;
    border-bottom: 1px solid;
  }

  button {
    background: none;
    border: none;
    padding: 0;
  }

  img {
    max-width: 100%;
    margin-top: 26px;
  }

  .project-text {
    margin: 12px 0;
  }

  .project-links {
    display: flex;
    gap: 1rem;
    margin-bottom: 28px;
  }

  .project-links a:hover, .project-links p:hover  {
  color: var(--text-color-hover);
}
</style>


<div class="accordion-item">
  <button class="accordion-header" on:click={() => toggle(index)}>
    <span>{project.name}</span>
    <span>{project.year}</span>
  </button>
  {#if isActive}
    <div class="accordion-content" transition:slide>
      <button on:click={() => toggle(index)} aria-label="Clickable Image">
        <img src={project.mediaSrc} alt={project.mediaAlt} loading="lazy">
      </button>
      <p class="project-text">{project.text}</p>
      <div class="project-links">
        {#if project.githubLink}
        <a href={project.githubLink} target="_blank" rel="noopener noreferrer">
          <p>Github</p>
        </a>
        {/if}
        {#if project.liveSiteLink}
        <a href={project.liveSiteLink} target="_blank" rel="noopener noreferrer">
          <p>Live Site</p>
        </a>
        {/if}
      </div>
    </div>
  {/if}
</div>