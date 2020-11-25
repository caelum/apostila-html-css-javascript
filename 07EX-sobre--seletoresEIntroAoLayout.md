# Exercício: Selecionando elementos mais específicos e herança

## Objetivo
      
No momento as figuras da página ocupam praticamente a largura da tela inteira. Nesse exercício, diminuiremos a largura das duas tags `<figure>` da página. Além das larguras, também alteraremos a disposição de cada figura na página. Cada uma terá uma largura e disposição diferentes.

A `<figure>` da matriz deverá ter **550px** de largura e deve estar centralizada em relação à página. A `<figure>` da família devera ter **275px** de largura, deve ficar alinhada à direita e envolta pelos textos que no HTML vêm abaixo dela.

Ao alterar a largura das tags `<figure>` você notará que as tags `<img>` dentro delas são maiores e ultrapassam a caixa da figura:

![A imagem da matriz é maior do que os 550px da <figure> {w=35}](assets/images/07-sobre--seletoresEIntroAoLayout/matriz_imagem_estourando_caixa.png)


Para resolver isso podemos dizer que toda tag `<img>` dentro de uma tag `<figure>` deve ocupar todo o espaço que definimos, mas não mais que isso.

O resultado final será assim:

![Resultado final da figura da matriz {w=40}](assets/images/07-sobre--seletoresEIntroAoLayout/matriz_menor.png)

![Resultado final da figura da família {w=40}](assets/images/07-sobre--seletoresEIntroAoLayout/familia_menor.png)

## Passo a passo com código

1. No arquivo **`sobre.css`** na pasta **`css`** faça as seguintes alterações:

    ###### # css/sobre.css
    ```css
     body {
       width: 940px;
       margin-left: auto;
       margin-right: auto;
     
       font-family: "Helvetica", "Lucida Grande", sans-serif;
       color: #3D3D3D;
     }
     
     h1 {
       padding: 10px;
     
       background-color: #E1EDF2;
     }
     
     h2 {
       border-bottom: 2px solid black;
     }
     
     figure {
       margin: 30px;
       padding: 15px;
       
       text-align: center;
     
       background-color: whitesmoke;
       border: 1px solid lightgrey;
     }
     
     figcaption {
       margin-top: 10px;
     }
    +
    +.matriz-musicdot {
    +  width: 550px;
    +  margin-left: auto;
    +  margin-right: auto;
    +}
    +
    +.familia-tupfeln {
    +  width: 275px;
    +  float: right;
    +}
    +
    +figure img {
    +  width: 100%;
    +}
    ```

2. No arquivo **`sobre.html`** na pasta **`raíz do projeto`** faça as seguintes alterações:

    ###### # sobre.html
    ```html
     <!doctype html>
     <html lang="pt-BR">
       <head>
         <meta charset="utf-8">
         <title>
           MusicDot | Sobre a empresa
         </title>
         <link href="img/favicon.ico" rel="icon">
         <link rel="stylesheet" href="css/sobre.css">
       </head>
       
       <body>
         
         <img src="img/logo.svg" alt="MusicDot">
         
         <h1> Sobre a empresa </h1>
         
         <p>
           A MusicDot é a maior escola online de música em todo o mundo.
           Fundada em 1932, possui estúdios em 124 países, sendo líder de mercado com mais de 90% de
           participação em 118 deles.
         </p>
         
         <p>
           Nossa matriz fica em <a href="https://maps.google.com.br/?q=190,GabrielDequech,Mafra,SC"> Mafra, em Santa Catarina </a>. De lá, saem grande parte das gravações de nossos cursos. Nossa matriz:
         </p>
     
    -    <̶f̶i̶g̶u̶r̶e̶>̶
    +    <figure class="matriz-musicdot">
           <img src="img/matriz-musicdot.png" alt="Matriz da musicdot">
           <figcaption>
               Matriz MusicDot 
           </figcaption>
         </figure>
         
         <p>
           Assine os cursos da MusicDot. Acesse <a href="index.html"> nosso site </a> ou entre em contato
           se tiver dúvidas. Conheça também <a href="#historia"> nossa história </a> e <a href="#diferenciais"> nossos diferenciais </a>.
         </p>
     
         <h2 id="historia"> História </h2>
     
    -    <̶f̶i̶g̶u̶r̶e̶>̶
    +    <figure class="familia-tupfeln">
           <img src="img/familia-tupfeln.jpg" alt="Foto da família tüpfeln">
           <figcaption>Família Tüpfeln</figcaption>
         </figure>
         
         <p>
           A fundação em 1932 ocorreu no momento da descoberta econônica de cursos por stream online no interior de Santa Catarina. A
           família Tüpfeln, tradicional da região, investiu todas as suas economias nessa nova iniciativa,
           revolucionária para a época. A fundadora frau Dagmar Olaf Tüpfeln, dotada de particular visão
           administrativa, guiou os negócios da empresa durante mais de 50 anos, muitos deles ao lado
           de seu filho Ernst Noten Tüpfeln, atual CEO. O nome da empresa é inspirado no nome da família.
         </p>
         
         <p>
           O crescimento da empresa foi praticamente instantâneo. Nos primeiros 5 anos, já atendia 18 países.
           Bateu a marca de 100 países em apenas 15 anos de existência. Até hoje, já atendeu 2 bilhões
           de usuários diferentes, em bilhões de diferentes pedidos.
         </p>
         
         <p>
           O crescimento em número de funcionários é também assombroso. Hoje, é a maior empregadora do
           Brasil, mas mesmo após apenas 5 anos de sua existência, já possuía 30 mil funcionários. Fora do
           Brasil, há 240 mil funcionários, além dos 890 mil brasileiros nas instalações de Mafra e
           nos escritórios em todo país.
         </p>
         
         <p>
           Dada a importância econômica da empresa para o Brasil, a família Tüpfeln já recebeu diversos prêmios,
           homenagens e condecorações. Todos os presidentes do Brasil já visitaram as instalações da MusicDot, além de presidentes da União Européia, Ásia e o secretário-geral da ONU.
         </p>
     
         <h2 id="diferenciais"> Diferenciais </h2>
         <ul>
           <li> Menor preço do mercado, garantido </li>
           <li> Se você achar um serviço mais barato, leva 1 mês de graça </li>
           <li> Pague em reais, dólares, euros, libras, dodgecoins, litecoins ou bitcoins </li>
           <li> Todas as compras acompanham acesso à Alura </li>
           <li> Maior escola de música online do mundo </li>
           <li> Atendimento via telefone, email, chat, twitter, facebook, instagram, ICQ, WhatsApp, SMS, carta, fax, sinal de fumaça e telegrama </li>
           <li> Presente em 124 países </li>
           <li> Mais de um milhão de funcionários em todo o mundo </li>
         </ul>
       </body>
     </html>
    ```
