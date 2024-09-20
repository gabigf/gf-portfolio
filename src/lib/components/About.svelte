<script>
  const coreListItems = [
    'Front end Development',
    'Framework-Agnostic',
    'Preference for Vue',
    'Component-Driven development',
    'Collaborative and Open to Learning'
  ]

</script>


<style>
.core-container {
  margin-bottom: 3rem
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>


<div class="core-container">
  <p>Core:</p>
  <ul>
    {#each coreListItems as item}
      <li>{item}</li>
    {/each}
  </ul>
</div>
