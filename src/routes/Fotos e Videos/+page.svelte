<script>
  import { fade } from 'svelte/transition';

  // Lista de imagens e vídeos (substitua com os reais)
  const midia = [
    { type: "image", src: "/imagens/photo1.png ", name: "hero.png" },
    { type: "image", src: "/imagens/photo1.png", name: "photo1.png" },
    { type: "video", src: "/videos/background.mp4", name: "background.mp4" }
  ];

  // Função para baixar arquivos
  function downloadMedia(item) {
    const link = document.createElement("a");
    link.href = item.src;
    link.download = item.name;
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
  }
</script>

<style>
  .container {
    text-align: center;
    padding: 50px;
    color: white;
    font-family: "Caveat", serif;
    background: url('/imagens/background_gallery.jpg') no-repeat center center fixed;
    background-size: cover;
    min-height: 100vh;
  }

  h1 {
    font-size: 4em;
    margin-bottom: 30px;
  }

  .gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
    padding: 20px;
  }

  .media-container {
    position: relative;
    text-align: center;
  }

  img, video {
    width: 100%;
    border-radius: 10px;
    transition: transform 0.3s ease;
  }

  img:hover, video:hover {
    transform: scale(1.05);
  }

  /* Botão estilizado */
  .download-btn {
    margin-top: 12px;
    padding: 10px 20px;
    background: linear-gradient(135deg, #c79a6d, #a07850);
    border: none;
    border-radius: 30px;
    cursor: pointer;
    color: white;
    font-size: 18px;
    font-weight: bold;
    text-transform: uppercase;
    transition: all 0.3s ease-in-out;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.3);
    outline: none;
  }

  .download-btn:hover {
    background: linear-gradient(135deg, #d8a375, #b0865b);
    transform: translateY(-2px);
    box-shadow: 0px 6px 15px rgba(0, 0, 0, 0.4);
  }

  a {
    color: #c79a6d;
    font-size: 1.5em;
    display: block;
    margin-top: 30px;
    text-decoration: none;
  }
</style>

<div class="container" transition:fade>
  <h1>Fotos e Vídeos</h1>
  
  <div class="gallery">
    {#each midia as item}
      <div class="media-container">
        {#if item.type === "image"}
          <img src={item.src} alt="Foto da sala" />
        {:else}
          <video controls>
            <source src={item.src} type="video/mp4">
          </video>
        {/if}
        <button class="download-btn" on:click={() => downloadMedia(item)}>Baixar</button>
      </div>
    {/each}
  </div>

  <a href="/">Voltar ao Início</a>
</div>
