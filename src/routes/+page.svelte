<script>
    import Button from "$lib/components/Button.svelte";
  </script>
  
  <section class="hero">
    <img src="/images/profile.jpg" alt="Foto de perfil" class="profile-img" />
    <h1>Bem-vindo ao Meu Portfólio!</h1>
    <p>Explore meus projetos e entre em contato.</p>
    <Button href="/sobre">Saiba Mais</Button>
  </section>
  
  <style>
    .hero {
      text-align: center;
      padding: 2rem;
    }
    .profile-img {
      width: 150px;
      height: 150px;
      border-radius: 50%;
      margin-bottom: 1rem;
    }
  </style>