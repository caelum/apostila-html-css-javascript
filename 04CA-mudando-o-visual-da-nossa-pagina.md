# Estilizando com CSS

Quando escrevemos o HTML, marcamos o conteúdo da página com tags que melhor representam
o significado daquele conteúdo. Quando abrimos a página no navegador é possível
perceber que ele mostra as informações com estilos diferentes.

Um h1, por exemplo, por padrão é apresentado em negrito numa fonte maior. Parágrafos de texto são espaçados entre si, e
assim por diante. Isso quer dizer que o navegador tem um _estilo padrão_ para as tags que usamos.
Porém para fazer sites bonitos, ou com o visual próximo de uma dada identidade visual (design), vamos precisar _personalizar a apresentação padrão dos elementos_ da página.

Antigamente, isso era feito no próprio HTML. Caso houvesse a necessidade de um título ser vermelho, era só fazer:

``` html
<h1><font color="red">MusicDot anos 90</font></h1>
```

Além da tag `<font>`, várias outras tags de estilo existiam. Mas isso é passado.
Hoje em dia **tags HTML para estilo são má prática** e jamais devem ser usadas, são interpretadas apenas para o modo de compatibilidade.

Em seu lugar, surgiu o **CSS** (_Cascading Style Sheet_ ou folha de estilos em cascata),
que é uma outra linguagem, separada do HTML, com
objetivo único de cuidar da estilização da página. A vantagem é que o CSS é bem
mais robusto que o HTML para estilização, como veremos. Mas, principalmente,
escrever formatação visual misturado com conteúdo de texto no HTML se mostrou algo impraticável. 
O CSS resolve isso separando as coisas; regras de estilo não aparecem mais no HTML, apenas no CSS.

## Sintaxe e inclusão de CSS

A sintaxe do CSS tem estrutura simples: é uma declaração de propriedades e valores separados por
um sinal de dois pontos ":", e cada propriedade é separada por um sinal de ponto e vírgula ";"
da seguinte maneira:

``` css
color: blue;
background-color: yellow;
```

O elemento que receber essas propriedades será exibido com o texto na cor azul e com
o fundo amarelo. Essas propriedades podem ser declaradas de três maneiras diferentes.

### Atributo style
A primeira delas é com o atributo `style` no próprio elemento:

``` html
<p style="color: blue; background-color: yellow;">
O conteúdo desta tag será exibido em azul com fundo amarelo no navegador!
</p>
```

Mas tínhamos acabado de discutir que uma das grandes vantagens do CSS era manter as
regras de estilo fora do HTML. Usando esse atributo `style` não parece que fizemos
isso. Justamente por isso não se recomenda esse tipo de uso na prática, mas sim os
que veremos a seguir.

### A tag style
A outra maneira de se utilizar o CSS é declarando suas propriedades dentro de uma tag `<style>`.

Como estamos declarando as propriedades visuais de um elemento em outro lugar do nosso documento,
precisamos indicar de alguma maneira a qual elemento nos referimos. Fazemos isso utilizando
um **seletor CSS**. É basicamente uma forma de buscar certos elementos dentro da página que
receberão as regras visuais que queremos.

No exemplo a seguir, usaremos o seletor que pega todas as tags `p` e altera sua cor e background:

``` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Sobre a MusicDot</title>
    <style>
      p {
        color: blue;
        background-color: yellow;
      }
    </style>
  </head>
  <body>
    <p>
      O conteúdo desta tag será exibido em azul com fundo amarelo!
    </p>
    <p>
      <strong>Também</strong> será exibido em azul com fundo amarelo!
    </p>
  </body>
</html>
```

O código dentro da tag `<style>` indica que estamos alterando a cor e o fundo de todos
os elementos com tag `p`. Dizemos que selecionamos esses elementos pelo nome de sua tag,
e aplicamos certas propriedades CSS apenas neles.

Revisando então a estrutura de uso do CSS:

``` css
seletor {
    propriedade: valor;
}
```

Algumas propriedades contém "subpropriedades" que modificam uma parte específica daquela propriedade que vamos trabalhar, sendo sua sintaxe:

``` CSS
seletor {
    propriedade-subpropriedade: valor;
}
```

No exemplo abaixo, em ambos os casos, trabalhamos com a propriedade `text`, que estiliza a aparência do texto do seletor informado. Podemos especificar quais propriedades específicas do texto queremos modificar, no caso `text-align` o alinhamento do texto, e com `text-decoration` colocamos o efeito de sublinhado.

``` css
p {
    text-align: center;
    text-decoration: underline;
}
```

### Arquivo externo

A terceira maneira de declararmos os estilos do nosso documento é com um arquivo externo com a extensão `.css`. Para que seja possível declarar nosso CSS em um arquivo à parte, precisamos indicar em nosso documento HTML uma ligação entre ele e a folha de estilo (arquivo com a extensão `.css`).

Além da melhor organização do projeto, a folha de estilo externa traz ainda as vantagens
de manter nosso HTML mais limpo e do reaproveitamento de uma mesma folha de estilos
para diversos documentos.

A indicação de uso de uma folha de estilos externa deve ser feita dentro da tag `<head>`
de um documento HTML:

``` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>MusicDot | Sobre a empresa</title>
    <!-- Inclusão do arquivo CSS -->
    <link rel="stylesheet" href="estilos.css">
  </head>
  <body>
    <p>
      O conteúdo desta tag será exibido em azul com fundo amarelo!
    </p>
    <p>
      <strong>Também</strong> será exibido em azul com fundo amarelo!
    </p>
  </body>
</html>
```

E dentro do arquivo `estilos.css` colocamos apenas o conteúdo do CSS:

``` css
p {
  color: blue;
  background-color: yellow;
}
```

## Propriedades tipográficas e fontes

Da mesma maneira que alteramos cores, podemos alterar o texto. Podemos definir fontes
com o uso da propriedade `font-family`.

A propriedade `font-family` pode receber seu valor com ou sem aspas dependendo da sua composição, por exemplo, quando uma fonte tem o nome separado por _espaço_.

Por padrão, os navegadores mais conhecidos exibem texto em um tipo que conhecemos como
"serif". As fontes mais conhecidas (e comumente utilizadas como padrão) são "Times" e
"Times New Roman", dependendo do sistema operacional. Elas são chamadas de **fontes
serifadas** pelos pequenos ornamentos em suas terminações.

Podemos alterar a família de fontes que queremos utilizar em nosso documento para
a família "sans-serif" (sem serifas), que contém, por exemplo, as fontes "Arial" e
"Helvetica". Podemos também declarar que queremos utilizar uma família de fontes
"monospace" como, por exemplo, a fonte "Courier".

_Obs: Fontes monospace podem ser tanto com serifa ou sem serifa. Monospace quer dizer apenas que todas as letras possuem o mesmo tamanho_

``` css
h1 {
  font-family: serif;
}

h2 {
  font-family: sans-serif;
}

p {
  font-family: monospace;
}
```

É possível, e muito comum, declararmos o nome de algumas fontes que gostaríamos de
verificar se existem no computador, permitindo que tenhamos um controle melhor da forma
como nosso texto será exibido. 

Em nosso projeto, as fontes não têm ornamentos, vamos declarar essa propriedade
para todo o documento por meio do seu elemento `body`:

``` css
body {
  font-family: "Helvetica", "Lucida Grande", sans-serif;
}
```

Nesse caso, o navegador verificará se a fonte "Helvetica" está disponível e a utilizará
para exibir os textos de todos os elementos do nosso documento que, por cascata,
herdarão essa propriedade do elemento `body`.

Caso a fonte "Helvetica" não esteja disponível,
o navegador verificará a disponibilidade da próxima fonte declarada, no nosso exemplo a
"Lucida Grande". Caso o navegador não encontre também essa fonte, ele solicita qualquer fonte
que pertença à família "sans-serif", declarada logo a seguir, e a utiliza para exibir o
texto, não importa qual seja ela.

Temos outras propriedades para manipular a fonte, como a propriedade `font-style`, que
define o estilo da fonte que pode ser: `normal`
(normal na vertical), `italic` (inclinada) e `oblique` (oblíqua).

<!--@note
Se algum aluno pedir exemplo da diferença entre itálico e oblíqua, pede para
ele entrar no Google Webfonts e procurar a fonte Libre Baskerville. Essa fonte
tem um itálico verdadeiro, que é diferente de uma fonte simplesmente inclinada.
-->

## Alinhamento e decoração de texto

Já vimos uma série de propriedades e subpropriedades que determinam o tipo e estilo
da fonte. Vamos conhecer algumas maneiras de alterarmos as disposições dos textos.

No exemplo a seguir vamos mudar o alinhamento do texto com a propriedade `text-align`.

``` css
p {
  text-align: right;
}
```

O exemplo determina que todos os parágrafos da nossa página tenham o texto
alinhado para a direita. Também é possível determinar que um elemento tenha seu
conteúdo alinhado ao centro ao definirmos o valor `center` para a propriedade
`text-align`, ou então definir que o texto deve ocupar toda a largura do
elemento aumentando o espaçamento entre as palavras com o valor `justify`. Por
padrão o texto é alinhado à esquerda, com o valor `left`, porém é
importante lembrar que essa propriedade propaga-se em cascata.

É possível configurar também uma série de espaçamentos de texto com o CSS:

``` css
p {
  line-height: 3px; /* tamanho da altura de cada linha */
  letter-spacing: 3px; /* tamanho do espaço entre cada letra */
  word-spacing: 5px; /* tamanho do espaço entre cada palavra */
  text-indent: 30px; /* tamanho da margem da primeira linha do texto */
}
```

## Imagem de fundo
A propriedade `background-image` permite indicar um arquivo de imagem para ser
exibido ao fundo do elemento. Por exemplo:

``` css
h1 {
  background-image: url(sobre-background.jpg);
}
```

Com essa declaração, o navegador vai requisitar um arquivo `sobre-background.jpg`, que deve estar
na mesma pasta do arquivo CSS onde consta essa declaração. Mas podemos também passar um endereço da web para pegar imagens remotamente:

``` css
body {
  background-image: url(https://i.imgur.com/uAhjMNd.jpg);
}
```

## Bordas

As propriedades do CSS para definirmos as **bordas** de um elemento nos apresentam
uma série de opções. Podemos, para cada borda de um elemento, determinar sua cor,
seu estilo de exibição e sua largura. Por exemplo:

``` css
body {
  border-color: red;
  border-style: solid;
  border-width: 1px;
}
```

A propriedade `border` tem uma forma resumida para escrever os mesmos estilos que
adicionamos acima, mas de uma maneira mais simples:

``` css
body {
  border: 1px solid red;
}
```

Para que o efeito da cor sobre a borda surta efeito, é necessário que a propriedade
`border-style` tenha qualquer valor diferente do padrão `none`.

Podemos também falar em qual dos lados do nosso elemento queremos a borda usando a subpropriedade que indica lado:

``` css
h1 {
  border-top: 1px solid red; /* borda vermelha em cima */
  border-right: 1px solid red; /* borda vermelha à direita */
  border-bottom: 1px solid red; /* borda vermelha embaixo */
  border-left: 1px solid red; /* borda vermelha à esquerda */
}
```

> Conseguimos fazer também comentários no CSS usando a seguinte sintaxe:
>
> ``` css
>     /* deixando o fundo amarelo ouro */
>     body {
>         background-color: gold;
>     }
> ```

<!-- comentário para separar quotes adjacentes -->

## Cores na Web

Propriedades como `background-color`, `color`, `border-color`, entre outras aceitam uma
cor como valor. Existem várias maneiras de definir cores quando utilizamos o CSS.

A primeira, mais simples, é usando o nome da cor:

``` css
h1 {
    color: red;
}

h2 {
    background-color: yellow;
}
```

O difícil é acertar a exata variação de cor que queremos no design e também cada navegador tem o seu padrão de cor para os nomes de cores. A W3C obriga que todos os navegadores tenham pelo menos 140 nomes de cores padronizados, mas existem mais de 16 milhões de cores na web e seria extremamente complicado nomear cada uma delas. Por isso, é bem incomum usarmos cores com seus nomes. O mais comum é definir a cor com base
em sua composição RGB.

RGB é o sistema de cor usado nos monitores, já que cada pixel nos monitores possuem 3 leds (um vermelho, um verde e um azul) e a combinação dessas 3 cores formam todas as outras 16 milhões de cores que vemos nos monitores. Podemos escolher a intensidade de cada um desses três leds
básicos, numa escala de 0 a 255.

Um amarelo forte, por exemplo, tem 255 de Red, 255 de Green e 0 de Blue (255, 255, 0).
Se quiser um laranja, basta diminuir um pouco o verde (255, 200, 0). E assim por diante.

No CSS, podemos escrever as cores tendo como base sua composição RGB. Aliás, no
CSS3 - que veremos melhor depois - há até uma sintaxe bem simples pra isso:

``` css
h3 {
    color: rgb(255, 200, 0);
}
```

Essa sintaxe funciona nos browsers mais modernos e até alguns browsers super antigos mas não é a mais comum na prática, por questões de compatibilidade. O mais comum é a **notação hexadecimal**. Essa sintaxe tem suporte universal nos navegadores e é mais curta de escrever, apesar de ser mais enigmática.

``` css
h3 {
    background-color: #f2eded;
}
```

No fundo, porém, as duas formas são baseadas no sistema RGB. Na notação hexadecimal
(que começa com **#**), temos 6 caracteres, os primeiros 2 indicam o canal Red, os
dois seguintes, o Green, e os dois últimos, Blue; ou seja, RGB. E usamos a matemática
pra escrever menos, trocando a base numérica de decimal para hexadecimal.

Na base hexadecimal, os algarismos vão de zero a quinze (ao invés do zero a nove da
base decimal comum). Para representar os algarismos de dez a quinze, usamos letras
de A a F. Nessa sintaxe, portanto, podemos utilizar números de 0-9 e letras de A-F.

Há uma conta por trás dessas conversões, mas seu editor de imagens deve ser capaz de
fornecer ambos os valores para você sem problemas. Um valor 255 vira FF na notação
hexadecimal. A cor **#f2eded**, por exemplo, é equivalente a **rgb(242, 237, 237)**,
um cinza claro.

Vale aqui uma dica quanto ao uso de cores hexadecimais, toda vez que os caracteres
presentes na composição da base se repetirem, estes podem ser simplificados. Então
um número em hexadecimal **3366ff**, pode ser simplificado para **36f**.

_Obs: os 3 pares de números devem ser iguais entre si, ou seja, se tivermos um hexadecimal #33aabc não podemos simplificar nada do código._
