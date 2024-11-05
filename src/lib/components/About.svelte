<script>
  const coreListItems = [
    'Full Stack Developer',
    'Framework-Agnostic',
    'Component-Driven Development',
    'Collaborative and Open to Learning',
  ]

</script>


<style>
.core-container {
  margin-bottom: 3rem
}

.core-title {
  font-weight: normal;
  margin-bottom: 12px;
}
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

li {
  margin-top: 2px;
}
</style>


<div class="core-container">
  <h3 class="core-title">A little about me:</h3>
  <ul>
    {#each coreListItems as item}
      <li>{item}</li>
    {/each}
  </ul>
</div>
