<script>
  import { onMount } from 'svelte';


  const themes = [
    { id: 'light', color: '#FCFCFC' }, // Light mode button
    { id: 'dark', color: '#050505' },  // Dark mode button
    { id: 'custom', color: '#0E60F9' } // Custom mode button
  ];

	let currentTheme = 'light';

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
		// Get theme from localStorage or default to 'light'
		if (typeof window !== 'undefined') {
			currentTheme = localStorage.getItem('theme') || 'light';
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
    margin: 5px;
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
