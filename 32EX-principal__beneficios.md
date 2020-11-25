# Exercício: Conteúdo Principal - os benefícios

## Objetivo
      
![Seção dos benefícios mobile {w=35}](assets/images/32-principal__beneficios/32-principal__beneficios_2020-02-26-14-27-04.png)

![Seção dos benefícios telas maiores {w=45}](assets/images/32-principal__beneficios/32-principal__beneficios_2020-02-26-14-27-36.png)

## Passo a passo com código

1. Crie o arquivo **`beneficios.css`** na pasta **`css`** com o seguinte código:

    ###### # css/beneficios.css
    ```css
    +.beneficios {
    +    text-align: center;
    +    margin-bottom: 2rem;
    +    padding: 0 10%;
    +    display: flex;
    +    flex-direction: column;
    +    align-items: center;
    +}
    +
    +.beneficios__titulo {
    +    font-size: 1rem;
    +    font-weight: 700;
    +}
    +
    +.beneficios__lista li {
    +    padding-top: 5.5rem;
    +    background-repeat: no-repeat;
    +    background-size: 4rem 4rem;
    +    background-position: top 20px center;
    +}
    +
    +.beneficio--paravoce {
    +    background-image: url(../img/icone-beneficios-tudo-para-voce.svg);
    +}
    +
    +.beneficio--duvidas {
    +    background-image: url(../img/icone-beneficios-nenhuma-duvida.svg);
    +}
    +
    +.beneficio--didatica {
    +    background-image: url(../img/icone-beneficios-didatica-cuidadosa.svg);
    +}
    +
    +.beneficio--online {
    +    background-image: url(../img/icone-beneficios-online.svg);
    +}
    +
    +.beneficio__titulo {
    +    font-size: .8rem;
    +    font-weight: 600;
    +    margin-top: 1rem;
    +    margin-bottom: .2rem;
    +}
    +
    +.beneficio__texto {
    +    line-height: 1rem;
    +}
    +
    +@media(min-width:768px) {
    +    .beneficios {
    +        margin-bottom: 3.7rem;
    +    }
    +    
    +    .beneficios__lista {
    +        display: grid;
    +        grid-template-columns: 17.5rem 17.5rem;
    +        gap: 1rem;
    +    }
    +    
    +    .beneficios__titulo {
    +        margin-bottom: 1rem;
    +    }
    +    
    +    .beneficio__titulo {
    +        font-size: 1.1rem;
    +    }
    +    
    +    .beneficio__texto {
    +        font-size: .8rem;
    +    }
    +}
    +
    +@media(min-width:1200px) {
    +    .beneficios__titulo {
    +        font-size: 1.3rem;
    +    }
    +    
    +    .beneficios__lista {
    +        gap: 1.3rem;
    +        grid-template-columns: 22.5rem 22.5rem;
    +    }
    +    
    +    .beneficios__lista li {
    +        padding-top: 7.25rem;
    +        background-size: 6rem 6rem;
    +    }
    +    
    +    .beneficio__titulo {
    +        font-size: 1.2rem;
    +        margin-bottom: .6rem;
    +    }
    +    
    +    .beneficio__texto {
    +        font-size: .9rem;
    +        line-height: 1.2rem;
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
         <link rel="stylesheet" href="css/video.css">
         <link rel="stylesheet" href="css/planos.css">
    +    <link rel="stylesheet" href="css/beneficios.css">
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
           <section class="video">
             <video  controls class="video--mobile" src="video/video-promocional.mp4" poster="img/video-principal-mobile.png"></video>
             <video controls class="video--desktop" src="video/video-promocional.mp4" poster="img/video-principal.png"></video>
             <article class="video__textos">
               <h2 class="textos__titulo">Estude com os melhores professores</h2>
               <p>Aprenda no seu ritmo, sem sair de casa</p>
             </article>
           </section>
           <section class="planos"> 
             <h2 class="planos__titulo">Acesso ilimitado a todos os cursos</h2>
             <article class="cards__planoanual">
               <span class="plano--destaque"> + Assinado</span>
               <div class="planos__card card--anual">
                 <h3 class="plano__titulo">Plano Anual</h3>
                 <p>12x <span class="valor--destaque">R$ 50,00</span></p>
                 <p>Valor total de R$ 600,00</p>
                 <span>Acesso à Alura Língua</span>
                 <a href="cursos.html" class="cards__botao botao">Matricule-se</a>
               </div>
             </article>
             <article class="planos__card card--semestral">
               <h3 class="plano__titulo">Plano Semestral</h3>
               <p>12x <span class="valor--destaque">R$ 60,00</span></p>
               <p>Valor total de R$ 360,00</p>
               <a href="cursos.html" class="cards__botao botao">Matricule-se</a>
             </article>
             <article class="planos__pagamentos">
               <p>Pagamento seguro com PayPal</p>
               <p>Oferecemos boleto à vista, <a href="#">basta entrar em contato</a></p>
             </article>
           </section>
    +      <section class="beneficios">
    +        <h2 class="beneficios__titulo">Porque estudar na Musicdot?</h2>
    +        <ul class="beneficios__lista">
    +          <li class="beneficio--paravoce">
    +            <h3 class="beneficio__titulo">Tudo para você realmente aprender</h3>
    +            <p class="beneficio__texto">Você acessa todo o conteúdo! São aulas, exercícios, playbacks, cifras, partituras e tira dúvidas. Estudem em qualquer lugar, qualquer dia, qualquer horário, ilimitado. Matricule-se já</p>
    +          </li>
    +          <li class="beneficio--duvidas">
    +            <h3 class="beneficio__titulo">Nenhuma dúvida sem resposta</h3>
    +            <p class="beneficio__texto">Dúvidas são importantes para o seu aprendizado, e as dificuldades são normais. Na MusicDot você estuda com todo o suporte necessário. Além de todo conteúdo, você tira dúvidas.</p>
    +          </li>
    +          <li class="beneficio--didatica">
    +            <h3 class="beneficio__titulo">Didática cuidadosa que te faz aprender</h3>
    +            <p class="beneficio__texto">Saber tocar não quer dizer saber ensinar. Na MusicDot você encontra os dois! Nosso orgulho é justo o extremo cuidado didático que temo com as aulas. Investimos muito tempo.</p>
    +          </li>
    +          <li class="beneficio--online">
    +            <h3 class="beneficio__titulo">Estudar online é a melhor opção</h3>
    +            <p class="beneficio__texto">Aprender em DVD e revistinha de banca são coisas do passado! Estudar com um professor particular é bom, mas quem é o seu professor? A MusicDot te oferece a melhor aula, a qualquer hora.</p>
    +          </li>
    +        </ul>
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
