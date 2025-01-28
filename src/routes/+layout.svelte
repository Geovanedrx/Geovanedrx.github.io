<script>
    export let title = "Meu Portfólio";
  </script>
  
  <svelte:head>
    <title>{title}</title>
    <link rel="stylesheet" href="/app.css">
  </svelte:head>
  
  <div class="layout">
    <Navbar />
    <main>
      <slot /> <!-- Conteúdo da página -->
    </main>
    <Footer />
  </div>
  
  <style>
    .layout {
      display: flex;
      flex-direction: column;
      min-height: 100vh;
    }
    main {
      flex: 1;
    }
  </style>