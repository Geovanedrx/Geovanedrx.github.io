<script>
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let years = ['Fotos Nossas'];
  let selectedYear = 'Fotos Nossas';

  const midia = {
    'Fotos Nossas': [
      { type: 'image', src: '/2023/foto1.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto2.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto3.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto4.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto5.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto6.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto7.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto8.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto9.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto10.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto11.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto12.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto13.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto14.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto15.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto16.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto17.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto18.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto19.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto20.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto21.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto22.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto23.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto24.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto25.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto26.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto27.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto28.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto29.png', name: '2023foto1.png' },
      { type: 'image', src: '/2023/foto30.png', name: '2023foto1.png' },
      { type: 'video', src: '/2023/video1.mp4', name: '2024_video1.mp4' },
      { type: 'video', src: '/2023/video2.mp4', name: '2024_video1.mp4' },
      { type: 'video', src: '/2023/video3.mp4', name: '2024_video1.mp4' },
      { type: 'video', src: '/2023/video4.mp4', name: '2024_video1.mp4' },
      { type: 'video', src: '/2023/video5.mp4', name: '2024_video1.mp4' },
      { type: 'video', src: '/2023/video6.mp4', name: '2024_video1.mp4' },
      { type: 'video', src: '/2023/video7.mp4', name: '2024_video1.mp4' },
      { type: 'video', src: '/2023/video8.mp4', name: '2024_video1.mp4' },
      { type: 'video', src: '/2023/video9.mp4', name: '2024_video1.mp4' }



    ],
    
  };

  function handleScroll() {
    document.querySelectorAll('.fade-in').forEach(el => {
      const rect = el.getBoundingClientRect();
      if (rect.top < window.innerHeight - 100) {
        el.classList.add('visible');
      }
    });
  }

  function downloadMedia(item) {
    const link = document.createElement("a");
    link.href = item.src;
    link.download = item.name;
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
  }

  onMount(() => {
    window.addEventListener('scroll', handleScroll);
  });
</script>

<style>
  .container {
    text-align: center;
    padding: 50px;
    color: rgb(0, 0, 0);
    font-family: "Caveat", serif;
    background: url('/videos/background.') no-repeat center center fixed;
    background-size: cover;
    min-height: 100vh;
    overflow-x: hidden;
  }

  h1 {
    font-size: 4em;
    margin-bottom: 30px;
  }

  .year-selector {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 20px;
    position: absolute;
    top: 20px;
    left: 50%;
    transform: translateX(-50%);
  }

  .year-selector span {
    font-size: 1.5em;
    padding: 10px 20px;
    cursor: pointer;
    transition: color 0.3s, transform 0.3s;
    color: rgb(0, 0, 0);
  }

  .year-selector span:hover {
    color: #d8a375;
    transform: scale(1.1);
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
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  img, video {
    width: 100%;
    height: 300px; /* Define altura fixa para uniformizar */
    object-fit: cover; /* Garante que as imagens não fiquem distorcidas */
    transition: transform 0.3s ease, opacity 0.3s ease;
    opacity: 1;
    border-radius: 10px;
  }

  img:hover, video:hover {
    transform: scale(1.05);
  }

  .download-btn {
    margin-top: 12px;
    padding: 12px 24px;
    background: linear-gradient(135deg, #d8a375, #9b5e3b);
    border: none;
    border-radius: 24px; /* Bordas arredondadas */
    cursor: pointer;
    color: white;
    font-size: 18px; /* Tamanho maior para destaque */
    font-family: 'Caveat', serif; /* Fonte estilosa */
    font-weight: bold;
    text-transform: uppercase;
    transition: all 0.3s ease-in-out;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
    outline: none;
  }

  .download-btn:hover {
    background: linear-gradient(135deg, #e0b085, #b5704a);
    transform: translateY(-2px);
    box-shadow: 0px 6px 15px rgba(0, 0, 0, 0.3);
  }

  .media-container {
    position: relative;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .fade-in {
  opacity: 1; /* Trocar para 1 para corrigir visibilidade inicial */
  transform: translateY(0);
  transition: opacity 0.8s ease-out, transform 0.8s ease-out;
}
  

  .fade-in.visible {
    opacity: 1;
    transform: translateY(0);
  }
 

  .footer {
    text-align: center;
    margin-top: 50px;
    padding: 20px;
  }

  .footer a {
     color: #c79a6d;
      font-size: 1.5em;
      margin-top: 20px;
      text-decoration: none;
  }

  .footer a:hover {
    text-decoration: underline;
  }

  @media (max-width: 768px) {
  .video-container {
    grid-template-columns: repeat(3, 1fr);
  }
}
.video-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* 3 colunas */
  gap: 10px; /* Espaçamento entre os vídeos */
  width: 100%;
}

.video-container video {
  width: 100%;
  height: auto;
}

</style>

<div class="container" transition:fade>
  <div class="year-selector">
    {#each years as year, index}
      <span on:click={() => selectedYear = year}>{year}</span>
    {/each}
  </div>
  <div class="gallery">
    {#each midia[selectedYear] as item}
      <div class="fade-in media-container">
        {#if item.type === "image"}
          <img src={item.src} alt="Fotos nossas" />
        {:else}
          <video controls>
            <source src={item.src} type="video/mp4">
          </video>
        {/if}
        <button class="download-btn" on:click={() => downloadMedia(item)}>Baixar</button>
      </div>
    {/each}
  </div>
  <div class="footer">
    <a href="/">Voltar ao Início</a>
  </div>
</div>