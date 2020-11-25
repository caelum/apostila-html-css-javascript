# Exercício: Embaralhando os itens do rodapé em telas maiores com Flexbox

## Objetivo
      
Agora, em telas a partir de **`640px`** precisamos alterar a disposição e a ordem em que os elementos do HTML aparecem na tela. Podemos fazer isso sem alterar o HTML, utilizando apenas o Flexbox.

O resultado final será o seguinte:

![Itens no rodapé com ordem diferente {w=45}](assets/images/26-rodape__responsivo--order--o-problema-da-especificide/26-rodape__responsivo--order.png)

## Passo a passo com código

1. No arquivo **`rodape.css`** na pasta **`css`** faça as seguintes alterações:

    ###### # css/rodape.css
    ```css
     .rodape {
       padding: 2em 5%;
     
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
     
    -.̶r̶o̶d̶a̶p̶e̶_̶_̶s̶e̶c̶a̶o̶ +̶ .̶r̶o̶d̶a̶p̶e̶_̶_̶s̶e̶c̶a̶o̶ {̶
    -  m̶a̶r̶g̶i̶n̶-̶t̶o̶p̶:̶ 2̶e̶m̶;̶
    -}̶
    -
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
    +
    +@media (max-width: 640px) {
    +  .rodape__secao + .rodape__secao {
    +    margin-top: 2em;
    +  }  
    +}
    +
    +@media(min-width: 640px) {
    +  .rodape {
    +    display: flex;
    +    flex-wrap: wrap;
    +    justify-content: space-between;
    +
    +    font-size: 1rem;
    +  }
    +
    +  .rodape__secao--sobre,
    +  .rodape__secao--cursos,
    +  .rodape__secao--links,
    +  .rodape__secao--newsletter {
    +    width: 45%;
    +  }
    +
    +  .rodape__secao--cursos {
    +    order: 1;
    +    margin: 0;
    +  }
    +
    +  .rodape__secao--links {
    +    order: 2;
    +    margin: 0;
    +  }
    +
    +  .rodape__secao--sobre {
    +    order: 3;
    +    margin-top: 2em;
    +  }
    +
    +  .rodape__secao--newsletter {
    +    order: 4;
    +    margin-top: 2em;
    +  }
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
         <link rel="stylesheet" href="css/cabecalho.css">
         <link rel="stylesheet" href="css/rodape.css">
         <link rel="stylesheet" href="css/form-newsletter.css">
       </head>
       <body>
     
         <header class="cabecalho">
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
     
         <footer class="rodape">
    -      <̶s̶e̶c̶t̶i̶o̶n̶ c̶l̶a̶s̶s̶=̶"̶r̶o̶d̶a̶p̶e̶_̶_̶s̶e̶c̶a̶o̶"̶>̶
    +      <section class="rodape__secao rodape__secao--sobre">
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
     
    -      <̶s̶e̶c̶t̶i̶o̶n̶ c̶l̶a̶s̶s̶=̶"̶r̶o̶d̶a̶p̶e̶_̶_̶s̶e̶c̶a̶o̶"̶>̶
    +      <section class="rodape__secao rodape__secao--cursos">
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
     
    -      <̶s̶e̶c̶t̶i̶o̶n̶ c̶l̶a̶s̶s̶=̶"̶r̶o̶d̶a̶p̶e̶_̶_̶s̶e̶c̶a̶o̶"̶>̶
    +      <section class="rodape__secao rodape__secao--links">
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
     
    -      <̶s̶e̶c̶t̶i̶o̶n̶ c̶l̶a̶s̶s̶=̶"̶r̶o̶d̶a̶p̶e̶_̶_̶s̶e̶c̶a̶o̶"̶>̶
    +      <section class="rodape__secao rodape__secao--newsletter">
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
