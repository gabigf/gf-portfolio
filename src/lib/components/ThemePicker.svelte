<script>
  import { onMount } from 'svelte';


  const themes = [
    { id: 'light', color: '#FCFCFC' },
    { id: 'dark', color: '#050505' },
    { id: 'custom', color: '#0E60F9' }
  ];

	let currentTheme = 'dark';

  // Reactive statement to only show the two buttons that are not active
  $: visibleThemes = themes.filter(theme => theme.id !== currentTheme);

  // Function to set theme and save it to localStorage
	function setTheme(newTheme) {
		currentTheme = newTheme;
		document.documentElement.className = newTheme;
		if (typeof window !== 'undefined') {
			localStorage.setItem('theme', newTheme);
		}
	}

  // Set the initial theme when the component loads
  onMount(() => {
		// Get theme from localStorage or default to 'dark'
		if (typeof window !== 'undefined') {
			currentTheme = localStorage.getItem('theme') || 'dark';
			document.documentElement.className = currentTheme;
		}
	});
</script>


<style>
  button {
    border: none;
    cursor: pointer;
    height: 16px;
    width: 16px;
    margin: 8px;
  }

  button:first-of-type  {
    margin-left: 0;
  }

  button:last-of-type  {
    margin-right: 0;
  }
</style>



<!-- Buttons Container -->
<div>
  {#each visibleThemes as theme}
    <button
      style="background-color: {theme.color};"
      on:click={() => setTheme(theme.id)}
    ></button>
  {/each}
</div>
