<script>
    let links = [
      { href: "/", label: "Início" },
      { href: "/sobre", label: "Sobre" },
      { href: "/contato", label: "Contato" },
    ];
  </script>
  
  <nav class="navbar">
    <div class="logo">Meu Portfólio</div>
    <ul>
      {#each links as { href, label }}
        <li><a href={href}>{label}</a></li>
      {/each}
    </ul>
  </nav>
  
  <style>
    .navbar {
      display: flex;
      justify-content: space-between;
      padding: 1rem 2rem;
      background: #333;
      color: #fff;
    }
    .navbar a {
      color: white;
      text-decoration: none;
      margin: 0 1rem;
    }
    .navbar a:hover {
      text-decoration: underline;
    }
  </style>