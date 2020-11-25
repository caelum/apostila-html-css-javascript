# Exercício: O componente container

## Objetivo
      
Olhe para sua página no navegador e volte aqui.

Você notou algum estilo se repetindo e que vamos continuar repetindo no resto da página? Se sim, como poderíamos deixar de repetir esse estilo?

Nesse exercício trataremos de um estilo repetido em específico: o espaçamento entre a página e o conteúdo do cabeçalho e do rodpé.

Para deixar de escrever o mesmo estilo várias vezes. Criaremos um novo componente/bloco chamado **`container`** que terá todos os estilos que criam esse espaçamento. Esse estilo será aplicado tanto no cabeçalho quanto no rodapé e será escrito apenas uma vez no novo componente **`container`**.

Nada deve mudar no visual da página. As mudanças serão apenas no código.

## Passo a passo com código

1. No arquivo **`cabecalho.css`** na pasta **`css`** faça as seguintes alterações:

    ###### # css/cabecalho.css
    ```css
     .cabecalho {
       text-align: center;
       font-size: 0.6rem;
       font-weight: bold;
       text-transform: uppercase;
       letter-spacing: 0.23em;
     
       color: #fff;
       background-color: #2D5377;
     }
     
     .cabecalho__logo {
       padding: 1.5em 0;
       width: 14.5em;
     }
     
     .cabecalho__menu {
       display: flex;
       justify-content: space-evenly;
       flex-wrap: wrap;
     
       background-color: #272B3A87;
     }
     
     .cabecalho__item-menu {
       display: inline-block;
     }
     
     .cabecalho__item-menu a {
       display: inline-block;
       padding: 1.86em 1.42em;
     }
     
     @media (min-width: 640px) {
       .cabecalho {
    -    p̶a̶d̶d̶i̶n̶g̶:̶ 0̶ 5̶%̶;̶
    +    padding-top: 0;
    +    padding-bottom: 0;
         display: flex;
         justify-content: space-between;
         align-items: center;
       }
     
       .cabecalho__logo {
         padding: 2.5em 0;
       }
     
       .cabecalho__menu {
         background-color: transparent; 
       }
     }
     
     @media (min-width: 770px) {
       .cabecalho__item-menu--matricular {
         margin-left: 1.42em;
     
         border-radius: 6px;
         background-color: #e93d50;
       }
     
       .cabecalho__item-menu--matricular a {
         padding: 1.8em 3.5em;
       }
     }
    -
    -@̶m̶e̶d̶i̶a̶ (̶m̶i̶n̶-̶w̶i̶d̶t̶h̶:̶ 1̶0̶6̶6̶p̶x̶)̶ {̶
    -  .̶c̶a̶b̶e̶c̶a̶l̶h̶o̶ {̶
    -    p̶a̶d̶d̶i̶n̶g̶-̶l̶e̶f̶t̶:̶ c̶a̶l̶c̶(̶(̶1̶0̶0̶%̶ -̶ 9̶6̶0̶p̶x̶)̶ /̶ 2̶)̶;̶
    -    p̶a̶d̶d̶i̶n̶g̶-̶r̶i̶g̶h̶t̶:̶ c̶a̶l̶c̶(̶(̶1̶0̶0̶%̶ -̶ 9̶6̶0̶p̶x̶)̶ /̶ 2̶)̶;̶
    -  }̶
    -}̶
    ```

2. Crie o arquivo **`container.css`** na pasta **`css`** com o seguinte código:

    ###### # css/container.css
    ```css
    +.container {
    +  padding-left: 5%;
    +  padding-right: 5%;
    +}
    +
    +@media (min-width: 1066px) {
    +  .container {
    +    padding-left: calc((100% - 960px) / 2);
    +    padding-right: calc((100% - 960px) / 2);
    +  }
    +}
    +
    +@media (min-width: 1440px) {
    +  .container {
    +    padding-left: calc((100% - 1200px) / 2);
    +    padding-right: calc((100% - 1200px) / 2);
    +  }
    +}
    ```

3. No arquivo **`rodape.css`** na pasta **`css`** faça as seguintes alterações:

    ###### # css/rodape.css
    ```css
     .rodape {
    -  p̶a̶d̶d̶i̶n̶g̶:̶ 2̶e̶m̶ 5̶%̶;̶
    +  padding-top: 2em;
    +  padding-bottom: 2em;
     
       text-align: center;
       font-size: 0.7rem;
     }
     
     .rodape__logo {
       width: 11.25em;
       margin-bottom: 1em;
     }
     
     .rodape__lista-midias-sociais {
       display: flex;
       justify-content: center;
     }
     
     .rodape__infos-empresa {
       line-height: 1.5;
     }
     
     .rodape__lista-midias-sociais {
       display: flex;
       justify-content: center;
       margin-top: 1em;
     }
     
     .rodape__item-midias-sociais {
       width: 2.62em;
       margin: 0 .25em;
     }
     
     .rodape__item-midias-sociais img {
       width: 100%;
     }
     
     .rodape__titulo {
       margin-bottom: 1em;
     
       font-size: 1.45em;
       font-weight: bold;
       text-transform: uppercase;
     }
     
     .rodape_item-lista {  
       font-weight: 500;
       margin: 0.625em 0;
     }
     
     @media (max-width: 640px) {
       .rodape__secao + .rodape__secao {
         margin-top: 2em;
       }  
     }
     
     @media(min-width: 640px) and (max-width: 1200px) {
       .rodape {
         display: flex;
         flex-wrap: wrap;
         justify-content: space-between;
     
         font-size: 1rem;
       }
     
       .rodape__secao--sobre,
       .rodape__secao--cursos,
       .rodape__secao--links,
       .rodape__secao--newsletter {
         width: 45%;
       }
     
       .rodape__secao--cursos {
         order: 1;
         margin: 0;
       }
     
       .rodape__secao--links {
         order: 2;
         margin: 0;
       }
     
       .rodape__secao--sobre {
         order: 3;
         margin-top: 2em;
       }
     
       .rodape__secao--newsletter {
         order: 4;
         margin-top: 2em;
       }
     }
     
     @media(min-width: 1200px) {
       .rodape {
         display: flex;
         justify-content: space-between;
         font-size: 0.85rem;
         
         text-align: left;
       }
     
       .rodape__titulo {
         font-size: 1em;
       }
     
       .rodape__lista-midias-sociais {
         justify-content: left;
       }
     
       .rodape__secao {
         margin-top: 0;
       }
     
       .rodape__secao + .rodape__secao {
         margin-left: 2em;
       }
     }
    ```

4. No arquivo **`index.html`** na pasta **`raíz do projeto`** faça as seguintes alterações:

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
    +    <link rel="stylesheet" href="css/container.css">
         <link rel="stylesheet" href="css/cabecalho.css">
         <link rel="stylesheet" href="css/rodape.css">
         <link rel="stylesheet" href="css/form-newsletter.css">
       </head>
       <body>
     
    -    <̶h̶e̶a̶d̶e̶r̶ c̶l̶a̶s̶s̶=̶"̶c̶a̶b̶e̶c̶a̶l̶h̶o̶"̶>̶
    +    <header class="cabecalho container">
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
           Conteúdo principal
         </main>
     
    -    <̶f̶o̶o̶t̶e̶r̶ c̶l̶a̶s̶s̶=̶"̶r̶o̶d̶a̶p̶e̶"̶>̶
    +    <footer class="rodape container">
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
