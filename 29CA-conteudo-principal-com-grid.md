# Display: grid

Mais uma propriedade de posicionamento de elementos! A propriedade `display: flex` já nos proporcionou grandes vantagens em relação às maneiras que costumávamos manipular posicionamento de elementos, só que encontramos uma certa complicação quando precisamos posicionar elementos de forma *bidimensional*. `Flex` é uma ótima ferramenta para quando temos elementos que precisam ser distribuídos de maneira igual e com uma direção bem definida.

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width">
    <title>Exemplo</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <main class="flex-container">
        <div class="foto"></div>
        <div class="foto"></div>
        <div class="foto"></div>
        <div class="foto"></div>
        <div class="foto"></div>
        <div class="foto"></div>
        <div class="foto"></div>
        <div class="foto"></div>
    </main>
</body>
</html>
```

```css
.flex-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
}

.foto {
    width: 200px;
    height: 200px;

    border-radius: 5px;

    box-shadow: 3px 3px 3px #000000aa;

    background-color: #ff002b;

    margin-bottom: 1rem;
}
```

No exemplo mostrado acima o `display: flex` funciona perfeitamente porque a distribuição é unidirecional, mesmo que exista uma segunda linha por conta do `flex-wrap`. Mas agora se vamos fazer algo como:

![](img-musicdot/grid/flex-problem.png)

`display: flex` por conta não consegue lidar o posicionamento *bidimensional*. Precisamos modificar a estrutura para que os elementos *ocupem o espaço de uma linha*:

```html
<main>
    <div class="flex-container"> <!-- Primeira linha que contém "apenas" o bloco verde e o container que guarda os elementos vermelhos-->
        <div class="foto foto-destaque-verde"></div> <!-- Bloco verde e primeiro elemento da linha -->
        <div class="flex-container foto-container"> <!-- Container que vai guardar o restante dos eleentos vermelhos e segundo elemento da linha -->
            <div class="foto"></div>
            <div class="foto"></div>
            <div class="foto"></div>
            <div class="foto"></div>
        </div>
    </div>
</main>
```

```css
.flex-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
}

.foto-container {
    width: 66%;
}

.foto {
    width: 200px;
    height: 200px;

    border-radius: 5px;

    box-shadow: 3px 3px 3px #000000aa;

    background-color: #ff002b;

    margin-bottom: 1rem;
}

.foto-destaque-verde {
    background-color: #24cc2d;

    height: 400px;
}
```

![](img-musicdot/grid/flex-solution.png)

Vamos entender o que aconteceu. Como o `flex` só consegue trabalhar com uma direção, então vamos criar a primeira linha contendo apenas dois elementos: o **bloco verde** e uma **caixa vazia**. Nessa caixa vazia, vamos criar nossa segunda linha (deixar a caixa como um `flex container`) com os 4 blocos vermelhos dentro e vamos limitar o tamanho dessa caixa para que o espaço seja melhor dividido. Já conseguimos perceber com esse exemplo simples que o código já começou a ficar muito complicado. Imagine fazer layouts mais complexos usando essa técnica do `diplay: flex`. Por conta dessa dificuldade de fazer layouts com uma complexidade *bidimensional* que surgiu o `display: grid`.

A idéia do `grid` é exatamente de não precisar mudar a estrutura do **HTML** e que toda a parte de posicionamento de layout fique apenas no **CSS**.

Quando colocamos a propriedade `display: grid` em um elemento ele se transforma em um *grid container* da mesma forma que um elemento se torna *flex container* quando recebe a propriedade `display: flex`. Depois que definimos um *grid container* precisamos definir sua estrutura. Por padrão um *grid container* coloca cada item em uma linha e todos eles ficam em uma coluna:

![](img-musicdot/grid/grid-container.png)

> Para ver melhor as marcações de grid, use a ferramenta de desenvolvimento de seu navegador.

Nós sabemos que nós precisamos de 3 colunas e 2 linhas para conseguir o efeito que queremos. Então vamos usar as propriedades de *grid container* que vão definir o número de colunas e o número de linhas respectivamente: `grid-template-columns:` e `grid-template-rows`. A propriedade de `grid` permite que nós usemos outra unidade de medida: `fr` (que significa fraction/ fração).

## grid-template-columns

Podemos colocar infinitos valores dentro dessa propriedade, mas cada valor dentro dessa propriedade vai representar **uma** coluna. Queremos 3 colunas que ocupem igualmente o espaço da página. Vamos usar a nova unidade de medida `fr`.

```css
.grid-container {
    display: grid;

    grid-template-columns: 1fr 1fr 1fr;
}
```

No código acima, quando escrevemos `1fr 1fr 1fr` estamos dizendo que queremos **3** colunas que ocupem 1 fração do espaço disponível, ou seja, cada coluna vai ter 1/3 do espaço disponível lateralmente.

## grid-template-rows

A propriedade que cria as linhas funciona da mesma maneira que a propriedade que cria colunas. Portanto se queremos duas linhas que ocupam o mesmo espaço:

```css
.grid-container {
    display: grid;

    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr;
}
```

Só que mesmo depois de ter colocado as duas linhas ainda assim os elementos não ficaram dispostos corretamente. O elemento verde ainda ocupa apenas uma linha e não duas, então precisamos indicar para o navegador:

```css
.foto-destaque-verde {
    background-color: #24cc2d;

    grid-row: span 2;

    height: 400px;
}
```

A propriedade `grid-row` é usada apenas nos elementos filhos de um *grid container* e ela recebe dois valores: linha de início e linha de término. No nosso exemplo usamos o valor `span` que diz que queremos mesclar linhas e o `2` a quantidade de linhas que vamos mesclar. Quando usamos o `span` o próximo valor vai ser a quantidade de linhas ou colunas que vamos mesclar, portanto não indicamos qual linha é a linha de término. Quando não colocamos o valor de término o navegador coloca automaticamente `span 1` que quer dizer "ocupe apenas 1 linha/coluna".

Agora sim nosso bloco verde está na posição correta em relação aos elementos vermelhos. Usado `grid` nós não precisamos mudar a estrutura HTML para conseguir o efeito que queríamos no começo e o código ficou muito mais simples de entender também.

Vamos dificultar um pouco nosso exemplo. Vamos trocar a posição do bloco verde para a direita. Vamos usar a propriedade `grid-columns` para dizer onde que queremos que nosso bloco verde comece e termine, mas apenas colocar essa propriedade no bloco verde não vai ser o suficiênte, precisamos colocar essa propriedade também nos blocos vermelhos e isso já começa a aumentar significativamente a complexidade e dificuldade de manutenção.

Para melhorar essa capacidade de movimentação de elementos dentro do grid, foi criado uma propriedade chamada *grid-template-areas*, que nomeia cada espaço do grid criado. Vamos pegar nosso layout normal e tentar nomear baseado no que já temos:

```css
.grid-container {
    display: grid;

    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    grid-template-areas:
        "verde vermelho vermelho"
        "verde vermelho vermelho";
}
```

Então no exemplo acima na primeira linha (o primeiro conjunto de aspas): `primeiro espaço: bloco verde, segundo espaço: bloco vermelho, terceiro espaço: bloco vermelho`; segunda linha (o segundo conjunto de aspas): `primeiro espaço: bloco verde, segundo espaço: bloco vermelho, terceiro espaço: bloco vermelho`. Agora só precisamos dizer quem é o bloco vermelho e quem é o bloco verde:

```css
.grid-container {
    display: grid;

    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    grid-template-areas:
        "verde vermelho vermelho"
        "verde vermelho vermelho";
}

.foto-destaque-verde {
    background-color: #24cc2d;

    /*
    grid-column: 4;
    grid-row: span 2;
    Esse código não é mais necessário por conta do grid-template-area
    */
    grid-area: verde;

    height: 400px;
}
```

Antes de colocar nome nos outros blocos, vamos nomear apenas o bloco verde e depois testar. Podemos observar que os elementos continuaram na mesma posição. Agora vamos mudar a posição do bloco verde:

```css
.grid-container {
    display: grid;

    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    grid-template-areas:
        "vermelho vermelho verde"
        "vermelho vermelho verde";
}

.foto-destaque-verde {
    background-color: #24cc2d;

    /*
    grid-column: 4;
    grid-row: span 2;
    Esse código não é mais necessário por conta do grid-template-area
    */
    grid-area: verde;

    height: 400px;
}
```

Mesmo sem nomear os blocos vermelhos com a propriedade `grid-area` chegamos no nosso objetivo. Neste caso só queremos mudar a posição do bloco verde e queremos que o restante se adapte conforme necessário, então podemos trocar os valores de **vermelho** para apenas um ponto "**.**" .

```css
.grid-container {
    display: grid;

    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    grid-template-areas:
        ". . verde"
        ". . verde";
}

.foto-destaque-verde {
    background-color: #24cc2d;

    /*
    grid-column: 4;
    grid-row: span 2;
    Esse código não é mais necessário por conta do grid-template-area
    */
    grid-area: verde;

    height: 400px;
}
```

> Não podemos deixar espaços vazios que o browser não vai entender, precisamos deixar alguma coisa para indicar o espaço do grid.
