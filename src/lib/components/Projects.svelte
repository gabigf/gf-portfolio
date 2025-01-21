<script>
   import { onMount } from 'svelte';
	import { Project } from '$lib';

  const projects = [
    {
      name: 'UX designer portfolio',
      year: '2024',
      mediaSrc: '/images/martine-portfolio.png',
      mediaType: 'image',
      mediaAlt: 'Screenshot of the crypto dashboard',
      text: '[WIP] A portfolio website for a local UX designer featuring GSAP scroll animations.',
      githubLink: null,
      liveSiteLink: 'https://www.martine.work/',
    },
    {
      name: 'Transaction tracker',
      year: '2024',
      mediaSrc: '/images/money-manager.png',
      mediaType: 'image',
      mediaAlt: 'Screenshot of home page',
      text: 'I wanted to learn the Quasar UI library so I made this transaction tracker.',
      githubLink: 'https://github.com/gabigf/quasar-app/blob/main/README.md',
      liveSiteLink: 'https://money-manager-ruddy.vercel.app/#/',
    },
    {
      name: 'Pizza n Go',
      year: '2021',
      mediaSrc: '/images/pizzaNGo.png',
      mediaType: 'image',
      mediaAlt: 'another project alt',
      text: 'A full stack application for a pizza restaurant. Users can order their pizzas and owners can manage orders and send notifications for order status.',
      githubLink: 'https://github.com/sidpatel93/Pizza-N-Go',
      liveSiteLink: null,
    },
    {
      name: 'Learning GSAP',
      year: '2024',
      mediaSrc: '/images/learning-gsap.png',
      mediaType: 'image',
      mediaAlt: 'Screenshot of project page',
      text: 'A simple project I made to document my learning of GSAP basics.',
      githubLink: "https://github.com/gabigf/learning-gsap/tree/main/CreativeCodingClub/GSAP3Express",
      liveSiteLink: null,
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
