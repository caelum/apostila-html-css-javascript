# Conhecendo padrões de CSS

Vimos já o conceito de desacoplar estilos usando classes e os benefícios que isso nos traz, mas para cada elemento que nós vamos estilizar precisamos pensar em um nome diferente e isso pode ficar muito complicado sem um padrão para seguir.

Existem vários padrões de CSS mas durante o curso vamos usar um chamado **_BEMCSS_**. A vantagem de se usar **_BEMCSS_** para quem está começando com desenvolvimento HTML e CSS é que ele é um padrão que foca bastante em estrutura e facilita bastante na hora planejar os nomes das classes.

**BEM** usa um conceito de `bloco__elemento--modificador` para nomear suas classes, sendo que `bloco` é o elemento html que representa uma divisão de conteúdo cuja sua existência já tenha um sentido por si só, `elemento` representa uma parte semântica do `bloco` e `modificador` é uma sinalização de _comportamento_ ou _estilização_.

> As divisões entre `bloco__elemento--modificador` são chamados de: double `snake__case` e double `kebab--case`. Quando queremos uma divisão como o _espaço_ usamos ou `kebab-case` ou o `camelCase`. `Kebab-case` é o mais comum para HTML e CSS e `camelCase` é mais comum em JavaScript.

Vamos ver como que **BEM** funciona com o exemplo abaixo:

``` html
<!-- section representa um painel (por exemplo) de produtos. Mas não de qualquer produto, mas sim de produtos mais vendidos -->
<section class="produtos produtos--mais-vendidos"> 
    <!-- O h2 representa o título desse painel -->
    <h2 class="produtos__titulo">Produtos mais vendidos</h2>
    <ul class="produtos__lista">
        <!-- li representa o produto em sí -->
        <li class="produtos__produto">
            <figure>
                <img src="img/produto1.png" alt="Foto do Produto 1">
                <figcaption>Foto do produto 1</figcaption>
            </figure>
        </li>
        <!-- li representa o produto em sí, mas nesse caso também temos um produto destaque -->
        <li class="produtos__produto produtos__produto--destaque">
            <figure>
                <img src="img/produto-destaque.png" alt="Foto do Produto em Destaque">
                <figcaption>Foto do produto em destaque</figcaption>
            </figure>
        </li>
        <li class="produtos__produto">
            <figure>
                <img src="img/produto3.png" alt="Foto do Produto 3">
                <figcaption>Foto do produto 3</figcaption>
            </figure>
        </li>
        <li class="produtos__produto">
            <figure>
                <img src="img/produto4.png" alt="Foto do Produto 4">
                <figcaption>Foto do produto 4</figcaption>
            </figure>
        </li>
    </ul>
</section>
```

Da maneira que montamos a estrutura acima fica bem fácil saber o que estamos estilizando no CSS. Veja a diferença:

``` css
section h2 { /* É o h2 da section que tem os produtos? E se precisar mudar minha estrutura para um h3? */
    font-size: 40px;
    font-weight: 800;
}
```

``` css
.produtos__titulo { /* Agora aqui eu sei que vou estilizar o título do painel de produtos. Mesmo se mudar para um h3 */
    font-size: 40px;
    font-weight: 800;
}
```

## Tipos de display

Existem 2 tipos de display que caracterizam a exibição padrão da maior parte dos elementos HTML: `display: block` e `display: inline`. A maneira mais fácil de ver a diferença entre eles é usando as tags que possuem essas propriedades por padrão, `<p>` e `<a>` respectivamente, e colocar uma cor de fundo.

**HTML:**  
``` html
<p>Um parágrafo que é block</p>
<a>Um link que é inline</a>
```

**CSS:**  
``` css
p {
    background-color: blue;   
}

a {
    background-color: red;
}
```

Veja o espaço que esses elementos realmente ocupam. A tag `<p>` ocupa toda a largura da página enquanto a tag `<a>` ocupa apenas o espaço necessário para mostrar o texto que colocamos. Vamos colocar mais elementos no nosso exemplo acima.

**HTML:**  
``` html
<p>Um parágrafo que é block</p>
<p>Mais um parágrafo que é block</p>
<a>Um link que é inline</a>
<a>Mais um link que é inline</a>
```

**CSS:**  
``` css
p {
    background-color: blue;   
}

a {
    background-color: red;
}
```

Podemos observar que agora um parágrafo ficou um embaixo do outro e os links ficaram um do lado do outro. Esses comportamentos são os esperados de elementos `block` e `inline`. Como um elemento `block` ocupa toda a largura da tela não podemos colocar outro elemento do lado porque não há espaço. Agora como no `inline` o elemento ocupa só o espaço necessário para mostrar nosso texto então podemos colocar outros elementos que caibam naquele espaço. Bom, vamos então resolver o problema de espaço da tag `<p>`:

**HTML:**  
``` html
<p>Um parágrafo que é block</p>
<p>Mais um parágrafo que é block</p>
<a>Um link que é inline</a>
<a>Mais um link que é inline</a>
```

**CSS:**  
``` css
p {
    background-color: blue;
    width: 30%;  
}

a {
    background-color: red;
    width: 60%;
}
```

Bom, agora temos dois problemas. Mesmo com o espaço extra os parágrafos não ficaram um do lado do outro e nossos links não tiveram alterações em suas larguras. Vamos usar o inspetor de elementos de nosso navegador para ver o que está acontecendo com esses elementos.

Selecionando a tag `<p>` com nosso inspetor conseguimos ver que ela realmente está ocupando `30%` do espaço da tela do navegador, mas agora tem alguma coisa a mais que não colocamos no CSS. **Margin**. Existe uma `margin` ocupando o restante do espaço que era ocupado pela tag `<p>`. Utilizando a propriedade `margin-right: 0px;` não parece fazer efeito. Mas está tudo bem! Esse é o comportamento esperado de um elemento `block`. 

Vamos ver agora o que aconteceu com nossos links. Nossos links parecem ter ignorado completamente a propriedade de largura que colocamos. Mais uma vez, está tudo bem! Esse é o comportamento padrão de um elemento `inline`. Diferente de um elemento `block`, um elemento `inline` não recebe propriedades de tamanho (`width` e `height`) e isso pode gerar alguns problemas com estilização. Foi criado então o `display: inline-block` que permite usar o melhor dos dois mundos. Vamos usar o exemplo acima novamente só que mudando o tipo de display do link:

**HTML:**  
``` html
<p>Um parágrafo que é block</p>
<p>Mais um parágrafo que é block</p>
<a>Um link que é inline</a>
<a>Mais um link que é inline</a>
```
**CSS:**  
``` css
p {
    background-color: blue;
    width: 30%;  
}

a {
    background-color: red;
    width: 60%;
    display: inline-block;
}
```

Perfeito! Agora nosso link recebeu o tamanho que colocamos e agora deixamos um `<a>` debaixo do outro. Se mudarmos o tamanho dessa tag `<a>` para um tamanho de `40%`, por exemplo, vemos que as nossas tags `<a>` ficam uma do lado da outra.

Em resumo então dos displays:

* `display: block`:
    - O elemento ocupa toda a largura disponível
    - Se diminuir o tamanho desse elemento o espaço restante será ocupado por uma `margin` não removível
    
* `display: inline`:
    - Permite que outro elemento fique do seu lado caso haja espaço
    - O elemento ocupa apenas o espaço para mostrar seu conteúdo
    - Não recebe propriedades de tamanho

* `display: inline-block`:
    - Permite que outro elemento fique do seu lado caso haja espaço
    - O elemento inicialmente ocupa apenas o espaço para mostrar seu conteúdo
    - Recebe propriedades de tamanho

### Quando devo usar `inline` ou `inline-block`?

O ideal é nunca limitar nossas opções quando vamos escolher uma propriedade. Se o único propósito de mudarmos o `display` de um elemento é para deixá-lo um do lado do outro, vamos usar `inline-block`. Se por algum motivo houver necessidade de mudar o tamanho desse elemento, já estamos com o `display` correto e não precisaremos mudá-lo de novo.
