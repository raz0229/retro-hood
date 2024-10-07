<script>
    import "../app.css";
    import Header from "$lib/components/header.svelte";
    import Footer from "$lib/components/footer.svelte";
    import { page } from "$app/stores"
  
    $: color = $page.url.pathname === '/process' 
                ? '#0a0909'
                : '#f8f8f8'


  </script>
  
<Header />


  <slot />

  <Footer 
    bgColor="{color}"
  />