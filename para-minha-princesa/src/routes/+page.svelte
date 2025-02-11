<script>
    import { fade } from 'svelte/transition';
    let showMenu = false;
  
    function toggleMenu() {
      showMenu = !showMenu;
    }
  
    function goToGallery() {
      setTimeout(() => {
        window.location.href = '/gallery';
      }, 300);
    }
  </script>
  
  <style>
    @media (max-width: 768px) {
      .year-selector {
        font-size: 1em;
        padding: 5px 10px;
      }
  
      .year-selector span {
        font-size: 1.2em;
        padding: 8px;
      }
  
      .gallery {
        grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      }
  
      img, video {
        max-width: 90vw;
      }
  
      .download-btn {
        font-size: 16px;
        padding: 8px 15px;
      }
    }
  
    html, body {
      height: 100%;
      margin: 0;
      padding: 0;
      overflow: hidden;
      font-family: 'Arial', sans-serif;
      color: white;
      width: 100vw;
      overflow-x: hidden;
    }
  
    .background {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background: url('/imagens/hero.png') no-repeat center center fixed;
      background-size: cover;
      z-index: -1;
    }
  
    .navbar {
      position: absolute;
      top: 20px;
      left: 20px;
      display: flex;
      flex-direction: column;
      gap: 10px;
    }
  
    .navbar a {
      color: white;
      text-decoration: none;
      font-size: 1.2em;
      transition: color 0.3s ease;
    }
  
    .navbar a:hover {
      color: #c79a6d;
    }
  
    .social-icons {
      position: absolute;
      top: 20px;
      right: 20px;
      display: flex;
      gap: 15px;
    }
  
    .social-icons img {
      width: 24px;
      height: 24px;
      transition: transform 0.3s ease;
    }
  
    .social-icons img:hover {
      transform: scale(1.2);
    }
  
    .hero {
      position: relative;
      width: 100vw;
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.7);
      overflow: hidden;
      font-family: "Caveat", serif;
    }
  
    .hero-content {
      text-align: center;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      line-height: 1.2;
      font-family: "Caveat", serif;
    }
  
    .hero h1 {
      font-family: "Caveat", serif;
      font-size: 3.5em;
      font-weight: bold;
      margin: 0;
    }
  
    .hero p {
      font-family: "Caveat", serif;
      font-size: 2em;
      font-weight: 400;
      margin: 5px 0;
    }
  
    .menu-icon {
      position: absolute;
      top: 50px;
      left: 20px;
      cursor: pointer;
      display: flex;
      flex-direction: column;
      gap: 5px;
      padding: 10px;
      border-radius: 5px;
      transition: background-color 0.3s ease;
      z-index: 1000;
    }
  
    .menu-icon:hover {
      background-color: rgba(255, 255, 255, 0.2);
    }
  
    .menu-icon div {
      width: 30px;
      height: 3px;
      background-color: white;
      transition: transform 0.3s ease, opacity 0.3s ease;
    }
  
    .menu-icon.active div:nth-child(1) {
      transform: rotate(45deg) translate(5px, 5px);
    }
  
    .menu-icon.active div:nth-child(2) {
      opacity: 0;
    }
  
    .menu-icon.active div:nth-child(3) {
      transform: rotate(-45deg) translate(5px, -5px);
    }
  
    .menu-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background-color: rgba(0, 0, 0, 0.8);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      opacity: 0;
      visibility: hidden;
      transition: opacity 0.3s ease, visibility 0.3s ease;
      z-index: 999;
      font-family: "Caveat", serif;
    }
  
    .menu-overlay.active {
      opacity: 1;
      visibility: visible;
    }
  
    .menu-overlay a {
      font-family: "Caveat", serif;
      color: white;
      font-size: 2em;
      text-decoration: none;
      margin: 20px;
      transition: color 0.3s ease, border 0.3s ease;
      padding: 10px 20px;
      border: 2px solid transparent;
    }
  
    .menu-overlay a:hover {
      color: #c79a6d;
      border: 2px solid #c79a6d;
      border-radius: 10px;
    }
  
    .video-background {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      max-width: 100%;
      overflow: hidden;
      height: 100vh;
      object-fit: cover;
      z-index: -1;
    }
  </style>
  
  <video autoplay loop muted playsinline class="video-background">
    <source src="/videos/background1.mp4" type="video/mp4">
  </video>
  
  <div class="menu-icon {showMenu ? 'active' : ''}" on:click={toggleMenu}>
    <div></div>
    <div></div>
    <div></div>
  </div>
  
  <div class="menu-overlay {showMenu ? 'active' : ''}">
    <a href="Fotos e Videos" transition:fade>Fotos e Vídeos</a>
  </div>
  
  <header class="hero">
    <nav class="navbar">
      <a href="/Sobre">Sobre</a>
    </nav>
    <div class="hero-content">
      <p>Para</p>
      <h1>Minha namorada ❤️</h1>
      <p>11/02/2025</p>
    </div>
  </header>
  