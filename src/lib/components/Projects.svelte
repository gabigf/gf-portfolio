<script>
   import { onMount } from 'svelte';
	import { Project } from '$lib';

  const projects = [
    {
      name: 'Money manager',
      year: '2024',
      mediaSrc: '/images/pizzaNGo.png',
      mediaType: 'image',
      mediaAlt: 'pizza N Go on 3 devices',
      text: 'I worked on this plugin for chatGPT that allows users to fly.',
      githubLink: 'github link here',
      liveSiteLink: 'live site link here',
    },
    {
      name: 'Personal portfolio',
      year: '2026',
      mediaSrc: '/images/pizzaNGo.png',
      mediaType: 'image',
      mediaAlt: 'another project alt',
      text: 'I worked on this plugin for chatGPT that allows users to poop.',
      githubLink: 'github link here',
      liveSiteLink: 'live site link here',
    },
    {
      name: 'Learning GSAP',
      year: '2026',
      mediaSrc: '/images/pizzaNGo.png',
      mediaType: 'image',
      mediaAlt: 'another project alt',
      text: 'I worked on this plugin for chatGPT that allows users to poop.',
      githubLink: 'github link here',
      liveSiteLink: 'live site link here',
    },
    {
      name: 'Hide Youtube thumbnail extension',
      year: '2026',
      mediaSrc: '/images/pizzaNGo.png',
      mediaType: 'image',
      mediaAlt: 'another project alt',
      text: 'I worked on this plugin for chatGPT that allows users to poop.',
      githubLink: 'github link here',
      liveSiteLink: 'live site link here',
    },
    {
      name: 'UX designer portfolio',
      year: '2026',
      mediaSrc: '/images/pizzaNGo.png',
      mediaType: 'image',
      mediaAlt: 'another project alt',
      text: 'I worked on this plugin for chatGPT that allows users to poop.',
      githubLink: 'github link here',
      liveSiteLink: 'live site link here',
    }
  ]
  onMount(() => {
    projects.forEach((project) => {
      const img = new Image();
      img.src = project.mediaSrc; // Preload the image
    });
  });


  let activeIndex = null;

  function toggle(index) {
    activeIndex = activeIndex === index ? null : index;
  }
</script>

<style>
  .section-title {
    font-weight: normal;
    margin: 12px 0;
  }


</style>


<div>
  <h3 class="section-title">Projects:</h3>
  {#each projects as project, index}
    <Project
      project={project}
      index={index}
      isActive={activeIndex === index}
      {toggle}
    />
  {/each}
</div>
