<script>
    import { fade } from 'svelte/transition';
  </script>
  
  <style>
    .container {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      text-align: center;
      color: rgb(0, 0, 0);
      font-family: "Caveat", serif;
      background: url('/imagens/background_about.jpg') no-repeat center center fixed;
      background-size: cover;
    }
  
    h1 {
      font-size: 4em;
      margin-bottom: 20px;
    }
  
    p {
      font-size: 1.8em;
      max-width: 800px;
      line-height: 1.5;
    }
  
    a {
      color: #c79a6d;
      font-size: 1.5em;
      margin-top: 20px;
      text-decoration: none;
    }
  </style>
  
  <div class="container" transition:fade>
    <h1>Para a Turma</h1>
    <p>Nossa turma está junta desde 2023, compartilhando risadas, brigas e conquistas. Agora, em 2025, estamos indo para o nosso ultimo ano, e espero que a gente construa memórias inesquecíveis.

        Criar este site foi uma forma de expressar o quanto amo essa turma. Sei que, um dia, cada um de nós seguirá seu próprio caminho, mas os momentos que vivemos aqui jamais serão esquecidos por mim. Este espaço foi feito para registrar nossa história, nossas fotos, nossos vídeos – tudo o que nos tornou uma família ao longo desses anos.
        
        Quando o tempo passar e a saudade bater, este site estará aqui, como um portal para reviver cada risada, cada trabalho em grupo e cada instante especial que compartilhamos.
        
        Informática 4B – IFMS 2025. Voces estarão para sempre em minhas memórias. 💙</p>
    <a href="/">Voltar ao Início</a>
  </div>