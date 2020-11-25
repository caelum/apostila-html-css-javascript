# Exercício: Conteúdo Principal

## Objetivo
      
![Seção vídeo em telas pequenas {w=35}](assets/images/30-principal__video/30-principal__video_2020-02-26-14-19-14.png)

![Seção vídeo em telas maiores {w=45}](assets/images/30-principal__video/30-principal__video_2020-02-26-14-19-47.png)

## Passo a passo com código

1. Crie o arquivo **`video.css`** na pasta **`css`** com o seguinte código:

    ###### # css/video.css
    ```css
    +.video {
    +    display: flex;
    +    flex-direction: column;
    +    align-items: center;
    +    text-align: center;
    +    color: #fff;
    +    background-color: #2a3042;
    +}
    +
    +.video--mobile {
    +    width: 100%;
    +    height: 8.9rem;
    +}
    +
    +.video--desktop {
    +    display: none;
    +}
    +
    +.video__textos {
    +    margin-top: 1rem;
    +    margin-bottom: 1rem;
    +    position: relative;
    +    padding: 0 10%;
    +    box-sizing: border-box;
    +}
    +
    +.textos__titulo {
    +    font-weight: 700;
    +    font-size: 1.2rem;
    +    margin-bottom: .3rem;
    +    margin-bottom: .5rem;
    +}
    +
    +.textos__titulo::first-line {
    +    color: #e93d50;
    +}
    +
    +@media(min-width:768px) {
    +    .video--mobile {
    +        display: none;
    +    }
    +    
    +    .video--desktop {
    +        display: block;
    +        width: 100%;
    +        height: 12.8rem;
    +    }
    +    
    +    .textos__titulo {
    +        font-size: 1.5rem;
    +    }
    +}
    +
    +@media(min-width:1200px) {
    +    .video--desktop {
    +        height: 19.8rem;
    +    }
    +    
    +    .video__textos {
    +        margin-top: 1.5rem;
    +        margin-bottom: 1.5rem;
    +    }
    +    
    +    .video__textos::before {
    +        width: 5rem;
    +        height: 5rem;
    +    }
    +    
    +    .textos__titulo {
    +        font-size: 1.9rem;
    +    }
    +}
    +
    +@media(min-width:1600px) {
    +    .video--desktop {
    +        height: 26.8rem;
    +    }
    +}
    ```

2. No arquivo **`index.html`** na pasta **`raíz do projeto`** faça as seguintes alterações:

    ###### # index.html
    ```html
     <!doctype html>
     <html>
       <head>
         <meta charset="utf-8">
         <meta name="viewport" content="width=device-width">
         <title>Musicdot</title>
         <link rel="icon" href="img/favicon.ico">
         <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Montserrat:300,400,500,600,700,&display=block">
         <link rel="stylesheet" href="css/reset.css">
         <link rel="stylesheet" href="css/container.css">
         <link rel="stylesheet" href="css/cabecalho.css">
         <link rel="stylesheet" href="css/cursos.css">
    +    <link rel="stylesheet" href="css/video.css">
         <link rel="stylesheet" href="css/rodape.css">
         <link rel="stylesheet" href="css/form-newsletter.css">
       </head>
       <body>
     
         <header class="cabecalho container">
           <a href="index.html">
             <img class="cabecalho__logo" src="img/musicdot-logo-light.svg" title="Ir para a página inicial da Musicdot" alt="Musicdot">
           </a>
           
           <nav>
             <ul class="cabecalho__menu">
               <li class="cabecalho__item-menu"> <a href="sobre.html#contato"> Contato </a> </li>
               <li class="cabecalho__item-menu"> <a href="#"> Entrar </a> </li>
               <li class="cabecalho__item-menu cabecalho__item-menu--matricular"> <a href="#"> Matricule-se </a> </li>
             </ul>
           </nav>
         </header>
     
         <main>
           <section class="cursos">
             <article class="cursos__chamada --largura-grande">
               <h1 class="chamada__titulo">Cursos online de <strong class="chamada__titulo--destaque">música</strong></h1>
               <p>Comece agora e aprenda sua primeira música em 10 minutos!</p>
               <a href="cursos.html" class="chamada__cursos__matricula botao">Matricule-se</a>
             </article>
             <nav>
                 <ul class="cursos__lista">
                     <li class="curso--tecladopiano">
                         <a href="#">Teclado & Piano</a>
                     </li>
                     <li class="curso--violaoguitarra">
                         <a href="#">Violão & Guitarra</a>
                     </li>
                     <li class="curso--baixo">
                         <a href="#">Baixo</a>
                     </li>
                     <li class="curso--bateria curso--destaque">
                         <a href="#">Bateria</a>
                     </li>
                     <li class="curso--percussao">
                         <a href="#">Percussão</a>
                     </li>
                     <li class="curso--canto curso--destaque2">
                         <a href="#">Canto</a>
                     </li>
                     <li class="curso--audio">
                         <a href="#">Áudio</a>
                     </li>
                     <li class="curso--teoria">
                         <a href="#">Teoria</a>
                     </li>
                     <li class="curso--sopro">
                         <a href="#">Sopro</a>
                     </li>
                     <li class="curso--cordas">
                         <a href="#">Cordas</a>
                     </li>
                 </ul>
             </nav>
           </section>
    +      <section class="video">
    +        <video  controls class="video--mobile" src="video/video-promocional.mp4" poster="img/video-principal-mobile.png"></video>
    +        <video controls class="video--desktop" src="video/video-promocional.mp4" poster="img/video-principal.png"></video>
    +        <article class="video__textos">
    +          <h2 class="textos__titulo">Estude com os melhores professores</h2>
    +          <p>Aprenda no seu ritmo, sem sair de casa</p>
    +        </article>
    +      </section>
         </main>
     
         <footer class="rodape container">
           <section class="rodape__secao rodape__secao--sobre">
             <img class="rodape__logo" src="img/logo.svg" alt="Logo da MusicDot">
     
             <p class="rodape__infos-empresa">
               AOVS Sistemas de Informática S.A.
               <br>
               CNPJ 05.555.382/0001-33 
               <br>
               Rua Vergueiro - São Paulo/SP
               <br>
               Telefone (11) 4118-3319
             </p>
     
             <ul class="rodape__lista-midias-sociais">
               <li class="rodape__item-midias-sociais">
                 <a href="https://www.facebook.com/musicdotonline">
                   <img src="img/footer-icone-facebook.svg" alt="MusicDot no Facebook">
                 </a>
               </li>
               <li class="rodape__item-midias-sociais">
                 <a href="https://www.youtube.com/user/musicdotonline">
                   <img src="img/footer-icone-youtube.svg" alt="MusicDot no YouTube">
                 </a>
               </li>
               <li class="rodape__item-midias-sociais">
                 <a href="https://www.instagram.com/musicdotonline/">
                   <img src="img/footer-icone-instagram.svg" alt="Instagram">
                 </a>
               </li>
             </ul>
           </section>
     
           <section class="rodape__secao rodape__secao--cursos">
             <h2 class="rodape__titulo"> Cursos da MusicDot </h2>
             <nav>
               <ul>
                 <li class="rodape_item-lista"><a href="#">Cursos de Teclado & Piano</a></li>
                 <li class="rodape_item-lista"><a href="#">Cursos de Violão/Guitarra</a></li>
                 <li class="rodape_item-lista"><a href="#">Cursos de Baixo</a></li>
                 <li class="rodape_item-lista"><a href="#">Cursos de Bateria</a></li>
                 <li class="rodape_item-lista"><a href="#">Cursos de Percussão</a></li>
                 <li class="rodape_item-lista"><a href="#">Cursos de Canto</a></li>
                 <li class="rodape_item-lista"><a href="#">Cursos de Áudio</a></li>
                 <li class="rodape_item-lista"><a href="#">Cursos de Teoria</a></li>
                 <li class="rodape_item-lista"><a href="#">Cursos de Sopro</a></li>
                 <li class="rodape_item-lista"><a href="#">Cursos de Cordas</a></li>
               </ul>
             </nav>
           </section>
     
           <section class="rodape__secao rodape__secao--links">
             <h2 class="rodape__titulo"> MusicDot </h2>
             <nav>
               <ul>
                 <li class="rodape_item-lista"><a href="#">Apostila</a></li>
                 <li class="rodape_item-lista"><a href="#">E-book</a></li>
                 <li class="rodape_item-lista"><a href="#">Login</a></li>
                 <li class="rodape_item-lista"><a href="#">Matricule-se</a></li>
                 <li class="rodape_item-lista"><a href="#">Perguntas frequentes</a></li>
                 <li class="rodape_item-lista"><a href="#">Para Escolas</a></li>
                 <li class="rodape_item-lista"><a href="#">Contato</a></li>
               </ul>
             </nav>
           </section>
     
           <section class="rodape__secao rodape__secao--newsletter">
             <h2 class="rodape__titulo"> 
               Receba novidades e lançamentos 
             </h2>
     
             <form action="#" method="get" class="form-newsletter">
               <label for="form-newsletter__label" class="form-newsletter__label">
                 Seu email pessoal
               </label>
               <input id="email-newsletter" name="email-newsletter" type="email" class="form-newsletter__campo">
               <button type="submit" class="form-newsletter__botao">
                 OK
               </button>
             </form>
           </section>
         </footer>
       </body>
     </html>
    ```
