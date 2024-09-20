<script>
	import { Project } from '$lib';

  const projects = [
    {
      name: 'Javascript',
      year: '2024',
      mediaSrc: '/images/pizzaNGo.png',
      mediaType: 'image',
      mediaAlt: 'pizza N Go on 3 devices',
      text: 'I worked on this plugin for chatGPT that allows users to fly.',
      githubLink: 'github link here',
      liveSiteLink: 'live site link here',
    },
    {
      name: 'Another Project',
      year: '2026',
      mediaSrc: 'none',
      mediaType: 'image',
      mediaAlt: 'another project alt',
      text: 'I worked on this plugin for chatGPT that allows users to poop.',
      githubLink: 'github link here',
      liveSiteLink: 'live site link here',
    }
  ]

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
