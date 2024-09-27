<script>
  import { ThemePicker, Projects, LastUpdated, About } from "$lib";

  const emailAddress = 'gabrielaguimaraesdev@gmail.com'
  const linkedInUrl = 'https://www.linkedin.com/in/gabriela-guimaraes-ferreira/'
  const githubUrl = 'https://github.com/gabigf'
  const readCvUrl = 'https://read.cv/explore'
</script>


<style>
.main-container {
  width: 600px;
}

nav {
  display: flex;
  justify-content: space-between;
  margin-top: 24px;
  margin-bottom: 5rem;
}

p {
  padding: 2px 0;
}

.top-right {
  display: flex;
  flex-direction: column;
  align-items: end;
}

.link-list {
  display: flex;
  gap: 1rem;
}

.link-text {
  text-decoration: none;
  color: inherit;
}

.link-text:hover {
  color: var(--text-color-hover);
}

@media screen and (max-width: 830px) {
  .main-container {
    padding-left: 24px;
  }

  nav {
    margin-bottom: 32px;
  }
}


@media screen and (max-width: 650px) {
  .main-container {
    width: 90%;
  }
  nav {
    flex-direction: column;
  }

  .top-right {
    align-self: start;
    align-items: start;
  }
}
</style>


<div class="main-container">
  <nav>
    <div>
      <p>{emailAddress}</p>
      <p>Based in Montréal, Canada.</p>
    </div>

    <div class="top-right">
      <div class="link-list">
        <p><a href="{linkedInUrl}" target="_blank" class="link-text">LinkedIn</a></p>
        <p><a href="{githubUrl}" target="_blank" class="link-text">Github</a></p>
        <p><a href="{readCvUrl}" target="_blank" class="link-text">Read.cv</a></p>
      </div>

      <ThemePicker />
    </div>
  </nav>

  <About />
  <Projects />
  <!-- <LastUpdated /> -->
</div>
