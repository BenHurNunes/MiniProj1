<template>
  <div id="app">
    <header>
      <h1>Ben-Hur Dutra Nunes</h1>
      <nav>
        <ul>
          <li><a @click.prevent="scrollTo('quemSouEu')" href="#">Quem Sou Eu</a></li>
          <li><a @click.prevent="scrollTo('oqueFaco')" href="#">O Que Faço</a></li>
          <li><a @click.prevent="scrollTo('hobbies')" href="#">Hobbies</a></li>
        </ul>
      </nav>
    </header>

    <main>
      <section id="quemSouEu">
        <img height="160" src="https://scontent-mad2-1.xx.fbcdn.net/v/t1.6435-9/69219460_2319016084818715_8162552068641390592_n.jpg?_nc_cat=111&ccb=1-7&_nc_sid=6ee11a&_nc_ohc=CoqPN6tmwxIQ7kNvgGm0cYI&_nc_zt=23&_nc_ht=scontent-mad2-1.xx&_nc_gid=AV6zKy8D6zZ1SgIt8s6lats&oh=00_AYBLDfm4G0RAaf8NRY12HwZS1zn_P4bjF-x2gWKfUptirQ&oe=67AF765F" alt="Foto de perfil">
        <h1>Quem Sou Eu</h1>
        <p>Me chamo <strong>Ben-Hur Dutra Nunes</strong>, tenho 25 anos e sou formado em audiovisual. Atualmente estou cursando um mestrado em Tecnologias Multimédias e pretendo ser um desenvolvedor web.</p>
      </section>

      <section id="oqueFaco">
        <h1>O Que Faço</h1>
        <p>Sou estudante e produtor digital freelancer. Já trabalhei na televisão como assistente de operações e operador de câmaras.</p>
      </section>

      <section id="hobbies">
        <h1>Hobbies</h1>
        <p>Sou apaixonado por jogos e por tecnologia. Tento sempre me manter atualizado com o que está sendo desenvolvido no mercado tech.</p>
      </section>
    </main>
  </div>
 
  <footer>
      <div class="social-media">
        <a href="https://www.facebook.com/benzinho.ch4v3"><img height="40" src="https://static.vecteezy.com/system/resources/previews/018/930/476/non_2x/facebook-logo-facebook-icon-transparent-free-png.png"></a>
        <a href="https://x.com/santuaryum"><img height="40" src="https://uxwing.com/wp-content/themes/uxwing/download/brands-and-social-media/x-social-media-black-icon.png"></a>
        <a href="https://www.linkedin.com/in/ben-hur-nunes/"><img height="40" src="https://cdn-icons-png.flaticon.com/512/174/174857.png"></a>
      </div>
    </footer>
</template>

<script>
export default {
  name: "SPA",
  methods: {
    scrollTo(sectionId) {
      const element = document.getElementById(sectionId);
      if (element) {
        element.scrollIntoView({ behavior: "smooth" });
      }
    },
  },
};
</script>

<style>
  body, ul, li, h1, p {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    font-family: "Lato", serif;
    line-height: 1.6;
    color: #333;
    background-color: #f4f4f9;
    scroll-behavior: smooth;
  }

  header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background: #333;
    color: #fff;
    z-index: 1000;
    display: flex;
    justify-content:space-between;
    align-items: center;
    padding: 20px;
  }

  header h1 {
    font-size: 1.8em;
  }

  header nav ul {
    list-style: none;
    display: flex;
    gap: 20px;
  }

  header nav ul li a {
    color: #fff;
    text-decoration: none;
    font-weight: bold;
    position: relative;
    padding: 5px 35px;
    transition: color 0.3s ease;
  }

  header nav ul li a.active::after,
  header nav ul li a:hover::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 2px;
    background: #00aaff;
    transition: width 0.3s ease;
  }

  header nav ul li a.active {
    color: #00aaff;
  }

  header nav ul li a:hover {
    color: #00aaff;
  }

  main {
    padding-top: 80px; 
  }

  section {
    padding: 40px 20px;
    margin: 40px auto;
    max-width: 800px;
    background: #fff;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  }

  section img {
    display: block;
    margin: 0 auto 20px;
    border-radius: 50%;
  }

  section h1 {
    font-size: 1.8em;
    color: #333;
    margin-bottom: 20px;
    text-align: center;
  }

  section p {
    font-size: 1.1em;
    line-height: 1.8;
    color: #555;
    text-align: justify;
  }

  footer {
    background: #333;
    color: #fff;
    text-align: center;
    padding: 20px;
    margin-top: 40px;
  }

  footer .social-media a {
    margin: 0 10px;
    display: inline-block;
    transition: transform 0.3s ease;
  }

  footer .social-media img {
    height: 40px;
    filter: invert(100%);
    transition: filter 0.3s ease, transform 0.3s ease;
  }

  footer .social-media a:hover img {
    filter: invert(50%);
    transform: scale(1.1);
  }


  section:target {
    animation: fadeIn 0.5s ease-in-out;
    outline: 2px solid #00aaff;
    outline-offset: -10px;
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(-20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @media (max-width: 768px) {
    header {
      flex-direction: column;
      align-items: flex-start;
    }

    header h1 {
      margin-bottom: 10px;
    }

    header nav ul {
      flex-direction: column;
      gap: 10px;
    }

    section {
      margin: 20px 10px;
      padding: 20px;
    }

    footer .social-media a {
      margin: 5px;
    }
  }

</style>
