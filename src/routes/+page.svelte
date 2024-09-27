<script>
  import '../app.css';
  import {  MainLayout, Logo } from '$lib'
  import { injectSpeedInsights } from '@vercel/speed-insights/sveltekit';

  injectSpeedInsights();
</script>

<Logo />
<MainLayout />
