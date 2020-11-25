# Exercício: Primeiros passos com HTML

## Objetivo
      
Começaremos a fazer nossa primeira página do projeto. Escreveremos o conteúdo e marcaremos ele com as *tags* do *HTML* para que nossa página tenha cada conteúdo diferenciado pela sua natureza. Nesse começo, o resultado será que cada conteúdo marcado terá um visual diferente por padrão, por exemplo, títulos aparecerão com um tamanho maior que o dos textos comuns.

Os conteúdos que aparecerão na página por enquanto serão:

* A logo da MusicDot
* O título principal da página: "Sobre a empresa"
* Os textos sobre a empresa, em parágrafos
* O subtítulo: "História"
* Os textos sobre a história, em parágrafos
* As figuras da empresa e da família. Lembrando que chamamos de figura o conjunto de uma foto e uma legenda.

Todo o conteúdo de texto das páginas já está pronto na pasta **"textos"**. Essa pasta foi disponibilizada juntamente com os arquivos do curso.

O resultado ao final do exercício será o seguinte:

![Visual da página ao final do exercício {w=50}](assets/images/02-sobre--inicioHTML/sobre--inicioHTML.png)

## Passo a passo com código

1. Crie o arquivo **`sobre.html`** na pasta **`raíz do projeto`** com o seguinte código:

    ###### # sobre.html
    ```html
    +<img src="img/logo.svg" alt="MusicDot">
    +
    +<h1> Sobre a empresa </h1>
    +
    +<p>
    +  A MusicDot é a maior escola online de música em todo o mundo.
    +  Fundada em 1932, possui estúdios em 124 países, sendo líder de mercado com mais de 90% de
    +  participação em 118 deles.
    +</p>
    +
    +<p>
    +  Nossa matriz fica em Mafra, em Santa Catarina. De lá, saem grande parte das gravações de nossos cursos. Nossa matriz:
    +</p>
    +
    +<figure>
    +  <img src="img/matriz-musicdot.png" alt="Matriz da musicdot">
    +  <figcaption> 
    +      Matriz MusicDot 
    +  </figcaption>
    +</figure>
    +
    +<p>
    +  Assine os cursos da MusicDot. Acesse nosso site ou entre em contato
    +  se tiver dúvidas. Conheça também nossa história e nossos diferenciais.
    +</p>
    +
    +<h2> História </h2>
    +
    +<figure>
    +  <img src="img/familia-tupfeln.jpg" alt="Foto da família tüpfeln">
    +  <figcaption>Família Tüpfeln</figcaption>
    +</figure>
    +
    +<p>
    +  A fundação em 1932 ocorreu no momento da descoberta econônica de cursos por stream online no interior de Santa Catarina. A
    +  família Tüpfeln, tradicional da região, investiu todas as suas economias nessa nova iniciativa,
    +  revolucionária para a época. A fundadora frau Dagmar Olaf Tüpfeln, dotada de particular visão
    +  administrativa, guiou os negócios da empresa durante mais de 50 anos, muitos deles ao lado
    +  de seu filho Ernst Noten Tüpfeln, atual CEO. O nome da empresa é inspirado no nome da família.
    +</p>
    +
    +<p>
    +  O crescimento da empresa foi praticamente instantâneo. Nos primeiros 5 anos, já atendia 18 países.
    +  Bateu a marca de 100 países em apenas 15 anos de existência. Até hoje, já atendeu 2 bilhões
    +  de usuários diferentes, em bilhões de diferentes pedidos.
    +</p>
    +
    +<p>
    +  O crescimento em número de funcionários é também assombroso. Hoje, é a maior empregadora do
    +  Brasil, mas mesmo após apenas 5 anos de sua existência, já possuía 30 mil funcionários. Fora do
    +  Brasil, há 240 mil funcionários, além dos 890 mil brasileiros nas instalações de Mafra e
    +  nos escritórios em todo país.
    +</p>
    +
    +<p>
    +  Dada a importância econômica da empresa para o Brasil, a família Tüpfeln já recebeu diversos prêmios,
    +  homenagens e condecorações. Todos os presidentes do Brasil já visitaram as instalações da MusicDot, além de presidentes da União Européia, Ásia e o secretário-geral da ONU.
    +</p>
    ```
