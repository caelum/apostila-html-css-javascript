# Listas HTML

Não são raros os casos em que queremos exibir uma listagem em nossas páginas. O HTML tem algumas
tags definidas para que possamos fazer isso de maneira correta. A lista mais comum é a lista
não-ordenada definida pela tag `<ul>` (_unordered list_).

``` html
<ul>
  <li>Primeiro item da lista</li>
  <li>
    Segundo item da lista:
    <ul>
      <li>Primeiro item da lista aninhada</li>
      <li>Segundo item da lista aninhada</li>
    </ul>
  </li>
  <li>Terceiro item da lista</li>
</ul>
```

Note que, para cada item da lista não-ordenada, utilizamos uma marcação de item de lista `<li>` (_list item_).
No exemplo acima, utilizamos uma estrutura composta na qual o segundo item da lista contém uma
nova lista. A mesma tag de item de lista `<li>` é utilizada quando demarcamos uma lista ordenada.

``` html
<ol>
  <li>Primeiro item da lista</li>
  <li>Segundo item da lista</li>
  <li>Terceiro item da lista</li>
  <li>Quarto item da lista</li>
  <li>Quinto item da lista</li>
</ol>
```

As listas ordenadas (`<ol>` - _ordered list_) também podem ter sua estrutura composta por outras listas ordenadas como no exemplo que temos para as listas não-ordenadas. Também é possível ter listas ordenadas aninhadas em um item de uma lista não-ordenada e vice-versa.


## Listas de definição
Existe um terceiro tipo de lista que devemos utilizar para demarcar um glossário, quando listamos
termos e seus significados. Essa lista é a **lista de definição** (_definition list_).

``` html
<dl>
  <dt>HTML</dt>
  <dd>
    HTML é a linguagem de marcação de textos utilizada
    para exibir textos como páginas na Internet.
  </dd>
  <dt>Navegador</dt>
  <dd>
    Navegador é o software que requisita um documento HTML
    através do protocolo HTTP e exibe seu conteúdo em uma
    janela.
  </dd>
</dl>
```

Para estilizar o formato padrão das listas ordenadas e não-ordenadas, podemos utilizar
a propriedade `list-style-type` no CSS:

  ``` css
  ul {
    /* alterar para circulo antes de cada <li> da lista não-ordenada */
    list-style-type: circle;
  }

  ol {
    /* alterar para uma sequência alfabética antes de cada <li> da lista ordenada */
    list-style-type: upper-alpha;
  }
  ```

> Também podemos usar a _shorthand property_ `list-style: circle`

## Links no HTML

Quando precisamos indicar que um trecho de texto se refere a um outro conteúdo,
seja ele no mesmo documento ou em outro endereço (por exemplo uma página na web), utilizamos a tag de âncora `<a>`.

Existem três diferentes usos para as âncoras. Um deles é a definição de links:

``` html
<p>
  Visite o site da <a href="https://www.caelum.com.br">Caelum</a>.
</p>
```

Note que a âncora está demarcando apenas a palavra **Caelum** de todo o conteúdo
do parágrafo exemplificado. Isso significa que, ao clicarmos com o cursor do
mouse na palavra **Caelum**, o navegador redirecionará o usuário para o site da
**Caelum**, indicado no atributo `href`.

> Podemos adicionar o atributo `target=""` para especificar onde que essa página irá carregar. Por padrão a página irá abrir na mesma aba da página que tem o link, mas se quisermos que a página abra em outra aba podemos colocar o valor `_blank` dentro desse atributo:
>
> ``` html
><a href="https://www.caelum.com.br" target="_blank">
>```

Outro uso para a tag de âncora é a demarcação de destinos para links dentro do próprio
documento, o que chamamos de **_bookmark_**.

``` html
<p>Mais informações <a href="#info">aqui</a>.</p>
<p>Conteúdo da página...</p>

<h2 id="info">Mais informações sobre o assunto:</h2>
<p>Informações...</p>
```

De acordo com o exemplo acima, ao clicarmos sobre a palavra **aqui**, demarcada com um link, o
usuário será levado à porção da página onde o _bookmark_ **info** é visível. _Bookmark_ é
o elemento que tem o atributo `id`.

É possível, com o uso de um link, levar o usuário a um _bookmark_ presente em outra página.

``` html
<a href="http://www.caelum.com.br/curso/wd43/#contato">
  Entre em contato sobre o curso
</a>
```

O exemplo acima fará com que o usuário que clicar no link seja levado à porção da página indicada
no endereço, especificamente no ponto onde o _bookmark_ **contato** seja visível.

O outro uso para a tag de âncora é a demarcação de destinos para links dentro do próprio
site, mas não na mesma página que estamos. Por exemplo, estamos na página **sobre.html** e
queremos um link para a página **index.html**.

``` html
<p>Acesse <a href="index.html">nossa loja</a>.</p>
```
