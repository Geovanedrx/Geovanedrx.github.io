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
      max-width: 90%;
      margin: auto;
      padding: 20px;
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

  /* Responsividade para celular */
  @media (max-width: 768px) {
      .container {
          height: auto;
          padding: 10px;
      }

      h1 {
          font-size: 2.5em;
      }

      p {
          font-size: 1.2em;
      }

      a {
          font-size: 1.2em;
      }
  }
</style>

<div class="container" transition:fade>
  <h1>Para minha gatinhaa</h1>
  <p>
      Meu amor, hoje completamos 2 anos e 1 mês juntos, e eu ainda não encontrei palavras que realmente expressem o quão sortudo sou por te ter.
      Desde o primeiro dia, você tem sido a melhor parte da minha vida. Cada momento ao seu lado é um presente que tenho imensa felicidade por ter.
      Já vivemos tantos momentos incríveis, nos apoiamos nos dias difíceis e espero que eu possa continuar partilhando a vida com vc. Eu olho para você e vejo meu futuro, vejo a pessoa que escolho todos os dias, e que escolheria sempre.
      Obrigado por ser exatamente quem você é, por me amar do jeito que ama, por fazer da minha vida um lugar mais bonito. Eu amo vc e não me canso de falar isso para vc, vc é incrível. Mal posso esperar por tudo que ainda vamos viver juntos.
      Para sempre nós. ❤️
  </p>
  <a href="/">Voltar ao Início</a>
</div>
