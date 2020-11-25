# Propriedades CSS

## Propriedade `font`

```css
.elemento {
    font-size: * px, em, rem, pt, %*; /* Controla o tamanho da fonte */
    font-weight: *0 à 1000. Depende da fonte*; /* Controla o peso da fonte */
    font-style: *normal, italic, oblique*;
    font-family: *serif, sans-serif, monospace, custom*; /* Controla a família da fonte */
}
```

## Propriedade `text`

```css
.elemento {
    text-align: *left, center, right, justify; /* Controla o alinhamento do texto */
    text-transform: *capitalize, uppercase, lowercase, none*; /* Controla a capitalização do texto */
    text-indent: *px, em, rem, %*; /* Controla o tamanho da indentação que é colocado antes de uma linha de texto em um bloco */
}
```

## Propriedade `letter-spacing`

```css
.elemento {
    letter-spacing: *px, rem, em, %, pt*; /* Controla o espaçamento entre uma letra e outra de um bloco de texto */
}
```

## Propriedade `line-height`

```css
.elemento {
    line-height: *pt, px, rem, em, sem unidade de medida*; /* Controla a altura das linhas de um conjunto de texto */
}
```

## Propriedades de cor

```css
.elemento {
    color: #ff00ff; /* Hexadecimal #RRGGBB */
    color: #f0f; /* Hexadecimal shorthand #RGB */
    color: rgb(255, 0, 255); /* Valor RGB de 0 a 255 rgb(R, G, B)*/
    color: #ff00ff00; /* Hexadecimal com opacidade (alpha) #RRGGBBAA */
    color: rgba(255, 0, 255, 0.0); /* Valor RGB com opacidade */
}
```

## Propriedade `background`

```css
.elemento {
    background-color: *hexadecimal, nome, rgb, rgba*; /* Controla a cor de fundo */
    background-image: *url()*; /* Coloca uma imagem como plano de fundo */
    background-size: *x y, x/y, cover, contain, %, px, rem, em *; /* Controla o tamanho do plano de fundo. Dois valores podem ser colocados, x e y ou apenas o valor de x que ele será adicionad/removido proporcionalmente em y */
    background-repeat: *repeat, no-repeat*; /* Controla se a imagem de fundo vai sofrer repetição*/
    background-position: *top right bottom left, top 10px, bottom 2rem right 2%*; /* Controla a posição do plano de fundo */
}
```

## Propriedade `border`

```css
.elemento {
    border: *espessura* *estilo* *cor*; /* Coloca uma borda em todo elemento */
    border-top: *espessura* *estilo* *cor*; /* Coloca uma borda acima do elemento */
    border-right: *espessura* *estilo* *cor*; /* Coloca uma borda à direita do elemento */
    border-bottom: *espessura* *estilo* *cor*; /* Coloca uma borda abaixo do elemento */
    border-left: *espessura* *estilo* *cor*; /* Coloca uma borda à esquerda do elemento */
}
```

## Propriedade `vertical-align`

```css
.elemento {
    vertical-align: *baseline, top, middle, bottom*; /* Alinha verticalmente elementos que são inline ou inline-block */
}
```

## Propriedades `width` e `height`

```css
.elemento {
    width: *px, rem, em, %*; /* Controla a largura do elemento */
    min-width: *px, rem, em, %*; /* Controla a largura mínima que um elemento pode ter */
    max-width: *px, rem, em, %*; /* Controla a largura máxima que um elemento pode ter */

    height: *px, rem, em, %*; /* Controla a altura do elemento */
    min-height: *px, rem, em, %*; /* Controla a altura mínima que um elemento pode ter */
    max-height: *px, rem, em, %*; /* Controla a altura máxima que um elemento pode ter */
}
```

## Propriedade `box-sizing`

```css
.elemento {
    box-sizing: *border-box, content-box*; /* Define qual caixa do box-model será usada como referência para colocar propriedades de tamanho */
}
```

## Propriedade `overflow`

```css
.elemento {
    overflow: *visible, hidden, scroll, auto*; /* Controla o comportamento dos elementos internos que "vazam"  do espaço definido pela tag mãe */
    overflow-x: *visible, hidden, scroll, auto*; /* Controla o comportamento dos elementos internos que "vazam"  do espaço horizontal definido pela tag mãe */
    overflow-y: *visible, hidden, scroll, auto*; /* Controla o comportamento dos elementos internos que "vazam"  do espaço vertial definido pela tag mãe */
}
```
