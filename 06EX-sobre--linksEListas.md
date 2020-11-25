# Exercício: Usando links e listas

## Objetivo
      
Criaremos uma nova seção no final da página que listará todos os diferenciais da MusicDot. Os textos de cada item dessa lista estão em **textos/sobre.txt**. Lembre-se que a ordem dos itens não é importante.

Agora que temos mais seções e bastante conteúdo, podemos melhorar a navegação e a experiência das pessoa que acessarem essa página. Adicionaremos vários links úteis no conteúdo que já temos.

No segundo parágrafo da página adicione um link ao redor de "Mafra, em Santa Catarina" que aponta para a localização ficticia da MusicDot no Google Maps: "http://maps.google.com.br/?q=190,GabrielDequech,Mafra,SC".

No terceiro parágrafo da página, adicione os seguintes links:
* "nosso site" apontando para a página principal do nosso site em "index.html"
* "nossa história" apontando para a página sobre, porém tendo como alvo o subtítulo `<h2> História </h2>`
* "nossos diferenciais" apontando para a página sobre, porém tendo como alvo o subtítulo `<h2> Diferenciais </h2>`

![Links com destaque nos parágrafos do início da página {w=75}](assets/images/06-sobre--linksEListas/links.png)

![Lista de diferenciais no final da página {w=75}](assets/images/06-sobre--linksEListas/lista_diferenciais.png)

## Passo a passo com código

1. Crie o arquivo **`index.html`** na pasta **`raíz do projeto`** com o seguinte código:

    ###### # index.html
    ```html
    +<h1> Página principal temporária da MusicDot </h1>
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
    -      N̶o̶s̶s̶a̶ m̶a̶t̶r̶i̶z̶ f̶i̶c̶a̶ e̶m̶ M̶a̶f̶r̶a̶,̶ e̶m̶ S̶a̶n̶t̶a̶ C̶a̶t̶a̶r̶i̶n̶a̶.̶ D̶e̶ l̶á̶,̶ s̶a̶e̶m̶ g̶r̶a̶n̶d̶e̶ p̶a̶r̶t̶e̶ d̶a̶s̶ g̶r̶a̶v̶a̶ç̶õ̶e̶s̶ d̶e̶ n̶o̶s̶s̶o̶s̶ c̶u̶r̶s̶o̶s̶.̶ N̶o̶s̶s̶a̶ m̶a̶t̶r̶i̶z̶:̶
    +      Nossa matriz fica em <a href="https://maps.google.com.br/?q=190,GabrielDequech,Mafra,SC"> Mafra, em Santa Catarina </a>. De lá, saem grande parte das gravações de nossos cursos. Nossa matriz:
         </p>
         
         <figure>
           <img src="img/matriz-musicdot.png" alt="Matriz da musicdot">
           <figcaption>
               Matriz MusicDot 
           </figcaption>
         </figure>
         
         <p>
    -      A̶s̶s̶i̶n̶e̶ o̶s̶ c̶u̶r̶s̶o̶s̶ d̶a̶ M̶u̶s̶i̶c̶D̶o̶t̶.̶ A̶c̶e̶s̶s̶e̶ n̶o̶s̶s̶o̶ s̶i̶t̶e̶ o̶u̶ e̶n̶t̶r̶e̶ e̶m̶ c̶o̶n̶t̶a̶t̶o̶
    -      s̶e̶ t̶i̶v̶e̶r̶ d̶ú̶v̶i̶d̶a̶s̶.̶ C̶o̶n̶h̶e̶ç̶a̶ t̶a̶m̶b̶é̶m̶ n̶o̶s̶s̶a̶ h̶i̶s̶t̶ó̶r̶i̶a̶ e̶ n̶o̶s̶s̶o̶s̶ d̶i̶f̶e̶r̶e̶n̶c̶i̶a̶i̶s̶.̶
    +      Assine os cursos da MusicDot. Acesse <a href="index.html"> nosso site </a> ou entre em contato
    +      se tiver dúvidas. Conheça também <a href="#historia"> nossa história </a> e <a href="#diferenciais"> nossos diferenciais </a>.
         </p>
     
    -    <̶h̶2̶>̶ H̶i̶s̶t̶ó̶r̶i̶a̶ <̶/̶h̶2̶>̶
    +    <h2 id="historia"> História </h2>
     
         <figure>
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
     
    +    <h2 id="diferenciais"> Diferenciais </h2>
    +    <ul>
    +      <li> Menor preço do mercado, garantido </li>
    +      <li> Se você achar um serviço mais barato, leva 1 mês de graça </li>
    +      <li> Pague em reais, dólares, euros, libras, dodgecoins, litecoins ou bitcoins </li>
    +      <li> Todas as compras acompanham acesso à Alura </li>
    +      <li> Maior escola de música online do mundo </li>
    +      <li> Atendimento via telefone, email, chat, twitter, facebook, instagram, ICQ, WhatsApp, SMS, carta, fax, sinal de fumaça e telegrama </li>
    +      <li> Presente em 124 países </li>
    +      <li> Mais de um milhão de funcionários em todo o mundo </li>
    +    </ul>
       </body>
     </html>
    ```
