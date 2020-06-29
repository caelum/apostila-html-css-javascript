# Propriedades CSS

## Propriedade `font`

```css
.elemento {
  /* Controla o tamanho da fonte */
  font-size: px, em, rem, pt, %;

  /* Controla o peso da fonte */
  font-weight: 0 à 1000. Depende da fonte; 
  font-style: normal, italic, oblique;

  /* Controla a família da fonte */
  font-family: serif, sans-serif, monospace, custom; 
}
```

## Propriedade `text`

```css
.elemento {
  /* Controla o alinhamento do texto */
  text-align: left, center, right, justify; 

  /* Controla a capitalização do texto */
  text-transform: capitalize, uppercase, lowercase, none;

  /* Controla o tamanho da indentação que é colocado antes de uma linha de texto em um bloco */
  text-indent: px, em, rem, %; 
}
```

## Propriedade `letter-spacing`

```css
.elemento {
  /* Controla o espaçamento entre uma letra e outra de um bloco de texto */
  letter-spacing: px, rem, em, %, pt; 
}
```

## Propriedade `line-height`

```css
.elemento {
  /* Controla a altura das linhas de um conjunto de texto */
  line-height: pt, px, rem, em, sem unidade de medida; 
}
```

## Propriedades de cor

```css
.elemento {
  /* Hexadecimal #RRGGBB */
  color: #ff00ff;
 
  /* Hexadecimal shorthand #RGB */
  color: #f0f; 

  /* Valor RGB de 0 a 255 rgb(R, G, B)*/
  color: rgb(255, 0, 255); 

  /* Hexadecimal com opacidade (alpha) #RRGGBBAA */
  color: #ff00ff00; 

  /* Valor RGB com opacidade */
  color: rgba(255, 0, 255, 0.0); 
}
```

## Propriedade `background`

```css
.elemento {
  /* Controla a cor de fundo */
  background-color: hexadecimal, nome, rgb, rgba; 

  /* Coloca uma imagem como plano de fundo */
  background-image: url(); 

  /* Controla o tamanho do plano de fundo. Dois valores podem ser colocados, x e y ou apenas o valor de x que ele será adicionad/removido proporcionalmente em y */
  background-size: x y, x/y, cover, contain, %, px, rem, em; 

  /* Controla se a imagem de fundo vai sofrer repetição*/
  background-repeat: repeat, no-repeat; 

  /* Controla a posição do plano de fundo */
  background-position: top right bottom left, top 10px, bottom 2rem right 2%; 
}
```

## Propriedade `border`

```css
.elemento {
  /* Coloca uma borda em todo elemento. 
    Para espessura use um número com uma unidade de medida. 
    Estilo pode ser: none, dashed, dotted, double, groove, inset, outset, solid.
    Cor pelas notações de cores (nome, hexadeciam, rgb ...)
 */
  border: espessura estilo cor; 

  /* Coloca uma borda acima do elemento */
  border-top: espessura estilo cor; 

  /* Coloca uma borda à direita do elemento */
  border-right: espessura estilo cor; 

  /* Coloca uma borda abaixo do elemento */
  border-bottom: espessura estilo cor;

  /* Coloca uma borda à esquerda do elemento */ 
  border-left: espessura estilo cor; 
}
```

## Propriedade `vertical-align`

```css
.elemento {
  /* Alinha verticalmente elementos que são inline ou inline-block */
  vertical-align: baseline, top, middle, bottom; 
}
```

## Propriedades `width` e `height`

```css
.elemento {
  /* Controla a largura do elemento */
  width: px, rem, em, %; 

  /* Controla a largura mínima que um elemento pode ter */
  min-width: px, rem, em, %; 

  /* Controla a largura máxima que um elemento pode ter */
  max-width: px, rem, em, %; 

  /* Controla a altura do elemento */
  height: px, rem, em, %; 

  /* Controla a altura mínima que um elemento pode ter */
  min-height: px, rem, em, %; 

  /* Controla a altura máxima que um elemento pode ter */
  max-height: px, rem, em, %; 
}
```

## Propriedade `box-sizing`

```css
.elemento {
  /* Define qual caixa do box-model será usada como referência para colocar propriedades de tamanho */
  box-sizing: border-box, content-box; 
}
```

## Propriedade `overflow`

```css
.elemento {
  /* Controla o comportamento dos elementos internos que "vazam"  do espaço definido pela tag mãe */
  overflow: visible, hidden, scroll, auto;

  /* Controla o comportamento dos elementos internos que "vazam"  do espaço horizontal definido pela tag mãe */ 
  overflow-x: visible, hidden, scroll, auto; 

  /* Controla o comportamento dos elementos internos que "vazam"  do espaço vertial definido pela tag mãe */
  overflow-y: visible, hidden, scroll, auto; 
}
```
