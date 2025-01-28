<script>
    let nome = "";
    let email = "";
    let mensagem = "";
    
    const enviarMensagem = () => {
      alert(`Obrigado, ${nome}! Sua mensagem foi enviada.`);
    };
  </script>
  
  <section class="contact">
    <h1>Entre em Contato</h1>
    <form on:submit|preventDefault={enviarMensagem}>
      <input type="text" bind:value={nome} placeholder="Seu Nome" required />
      <input type="email" bind:value={email} placeholder="Seu Email" required />
      <textarea bind:value={mensagem} placeholder="Sua Mensagem" required></textarea>
      <button type="submit">Enviar</button>
    </form>
  </section>
  
  <style>
    .contact {
      max-width: 600px;
      margin: auto;
      padding: 2rem;
    }
    form {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }
    input, textarea {
      padding: 0.5rem;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
  </style>