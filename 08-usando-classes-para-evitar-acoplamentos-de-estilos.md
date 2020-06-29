# Desacoplamento com classes

Muitas vezes quando estamos declarando os estilos de uma página HTML, achamos mais fácil usar o seletor de nome da tag ao invés de usar classes. Porém isto pode causar problemas imprevistos se não usado com cautela. 
Vamos analisar o seguinte código para entender a situação:  

**HTML:**  
``` html
<h1>MusicDot</h1>

<h2>História</h2>
<p>Texto</p>

<h2>Diferenciais</h2>
<ul>
    <li>Diferencial 1</li>
    <li>Diferencial 2</li>
    <li>Diferencial 3</li>
</ul>
```

**CSS:**  
``` css
h2 {
    font-size: 24px;
    font-weight: bold;
    border-bottom: 1px solid #000000;
}
```

No exemplo acima adicionamos estilo nas tags `<h2>` para ter um tamanho de fonte maior, uma fonte mais grossa e uma borda abaixo para fazer o efeito de linha divisória. Até aqui tudo certo. Mas agora vamos colocar um outro título na página chamada "Sobre a MusicDot" e esse título tem relevância maior do que os dois outros títulos que temos (História e Diferenciais), portanto vamos ter que modificar suas tags para uma de menos importância:

``` html
<h1>MusicDot</h1>

<h2>Sobre a MusicDot</h2>
<p>Introdução</p>

<!-- Mudamos para h3 pois queremos que tenham menos relevância que o título "Sobre a MusicDot" -->
<h3>História</h3>
<p>Texto</p>

<!-- Mudamos para h3 pois queremos que tenham menos relevância que o título "Sobre a MusicDot" -->
<h3>Diferenciais</h3>
<ul>
    <li>Diferencial 1</li>
    <li>Diferencial 2</li>
    <li>Diferencial 3</li>
</ul>
```

Agora com essa mudança da estrutura do HTML o nosso CSS está alterando um elemento que não é o que nós inicialmente queríamos mudar. Vamos ter que fazer a mudança no CSS para usar as nossas alterações no elemento certo. 

Neste exemplo a solução é relativamente simples, porém imagine que temos seletores bem mais complexos, com heranças etc... a mudança não seria tão simples. Por isso o ideal é declarar estilos com classes ao invés de  nomes de tags. Uma dica pra dar nome às classes é elas representarem o papel que estas tags estão exercendo em conjunto com os estilos declarados, no nosso caso, estamos declarando um conjunto de estilo para subtítulos. 

Veja como fica o resultado do desacoplamento do conjunto de estilos do nome da tag, para ser agora com classes:

**HTML:**  
``` html
<h1>MusicDot</h1>

<h2>Sobre a MusicDot</h2>
<p>Introdução</p>

<!-- Adicionamos a classe subtitulo-->
<h3 class="subtitulo">História</h3>
<p>Texto</p>

<!-- Adicionamos a classe subtitulo-->
<h3 class="subtitulo">Diferenciais</h3>
<ul>
    <li>Diferencial 1</li>
    <li>Diferencial 2</li>
    <li>Diferencial 3</li>
</ul>
```

**CSS:**  
``` css
.subtitulo {
    font-size: 24px;
    font-weight: bold;
    border-bottom: 1px solid #000000;
}
```

Usando classes, podemos alterar toda a estrutura HTML sem nos preocupar se estas alterações afetarão a estilização que fizemos no começo.
