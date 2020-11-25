# O processo de desenvolvimento de uma tela

Existe hoje no mercado uma grande quantidade de empresas especializadas no desenvolvimento
de sites e aplicações web, bem como algumas empresas de desenvolvimento de software ou
agências de comunicação que têm pessoas capacitadas para executar esse tipo de projeto.

Quando detectada a necessidade do desenvolvimento de um site ou aplicação web, a empresa
que tem essa necessidade deve passar todas as informações relevantes ao projeto para a
empresa que vai executá-lo. A empresa responsável pelo seu desenvolvimento deve
analisar muito bem essas informações e utilizar pesquisas para complementar ou mesmo
certificar-se da validade dessas informações.

Um projeto de site ou aplicação web envolve muitas disciplinas em sua execução, pois são
diversas características a serem analisadas e diversas as possibilidades apresentadas
pela plataforma. Por exemplo, devemos conhecer muito bem as características do público
alvo, pois ele define qual a melhor abordagem para definir a navegação, tom linguístico e
visual a ser adotado, entre outras. A afinidade do público com a Internet e o dispositivo
pode inclusive definir o tipo e a intensidade das inovações que podem ser utilizadas.

Por isso, a primeira etapa do desenvolvimento do projeto fica a cargo da pessoa que cuida da
experiência de usuário (UX Designer) junto com uma pessoa de Design e alguém de conteúdo. Esse grupo de
pessoas analisa e endereça uma série de informações da característica humana do projeto, definindo a
quantidade, conteúdo, localização e estilização de cada informação.

Algumas das motivações e práticas de Experiência do Usuário são conteúdo do curso **Design de Interação,
Experiência do Usuário e Usabilidade**. O resultado do trabalho dessa equipe é uma série de definições
sobre a navegação (mapa do site) e um esboço de cada uma das visões, que são os layouts das páginas, e
visões parciais como, por exemplo, os diálogos de alerta e confirmação da aplicação. Por essas visões
serem esboços ainda, a parte de estilo do site fica mais genérica: são utilizadas fontes, cores e
imagens neutras, embora as informações escritas devam ser definidas nessa fase do projeto.

Esses esboços das visões são o que chamamos de **wireframes** e guiam o restante do processo
de design.

Com os wireframes em mãos, é hora de adicionar as imagens, cores, fontes, fundos, bordas e
outras características visuais. Esse trabalho é realizado pela mesma equipe acima, só que agora sem a
pessoa de conteúdo, que utilizam ferramentas gráficas como Adobe Photoshop, Adobe Illustrator,
Figma, entre outras. O resultado do trabalho dessa equipe é que chamamos de **layout**. Os layouts
são imagens estáticas já com o visual completo a ser implementado.
Apesar de os navegadores serem capazes de exibir imagens estáticas, exibir uma única
imagem para o usuário final no navegador não é a forma ideal de se publicar uma página.

Para que as informações sejam exibidas de forma correta e para possibilitar outras formas de
uso e interação com o conteúdo, é necessário que a equipe de **programação front-end**
transforme essas imagens em telas visíveis e, principalmente, utilizáveis pelos
navegadores. 

De todas as tecnologias disponíveis, a mais recomendada é certamente o HTML, pois é a
linguagem que o navegador entende. Todas as outras tecnologias citadas dependem do HTML
para serem exibidas corretamente no navegador e, ultimamente, o uso do HTML, em conjunto com
o CSS e o JavaScript, tem evoluído a ponto de podermos substituir algumas dessas outras
tecnologias onde tínhamos mais poder e controle em relação à exibição de gráficos, efeitos
e interatividade.

## Analisando o Layout

Antes de digitar qualquer código, é necessária uma análise do layout. Com essa análise,
definiremos as principais áreas de nossas páginas. Note que há um cabeçalho (uma área que potencialmente se
repetirá em mais de uma página), um rodapé e um conteúdo principal. Seguindo o pensamento de escrever o nosso
código pensando em semântica em primeiro lugar, já podemos imaginar como que será a estrutura no
documento `html`

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width">
    <title>MusicDot</title>
</head>
<body>
    <header>
        <!-- Conteúdo do header -->
    </header>
    <main>
        <!-- Conteúdo principal -->
    </main>
    <footer>
        <!-- Conteúdo do footer -->
    </footer>
</body>
</html>
```

Uma recomendação é a de começar a planejar o código sempre analizando de fora para dentro. Portanto, depois de
ver as 3 principais camadas (`<header>`, `<main>` e `<footer>`) vamos nos aprofundar em uma delas. Vamos partir
da ordem de declaração e nos aprofundar mais na tag `<header>`. Dentro de `header` temos uma **logo** e 3
**links**. Sabemos já que a logo é uma **imagem**:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width">
    <title>MusicDot</title>
</head>
<body>
    <header>
        <!-- Conteúdo do header -->
        <img src="img/logo-musicdot.png" alt="Logo da MusicDot">
    </header>
    <main>
        <!-- Conteúdo principal -->
    </main>
    <footer>
        <!-- Conteúdo do footer -->
    </footer>
</body>
</html>
```

Agora com os links precisamos notar que são links que vão para outras páginas dentro do nosso próprio site
portanto esses 3 **links** fazem parte de uma **navegação** e que são 3 **links** em sequência. Quando temos
elementos iguais em sequência temos uma **lista**! Nesse nosso caso a ordem dos links não importa:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width">
    <title>MusicDot</title>
</head>
<body>
    <header>
        <!-- Conteúdo do header -->
        <img src="img/logo-musicdot.png" alt="Logo da MusicDot">
        <nav>
            <ul>
                <li><a href="#">Contato</a></li>
                <li><a href="#">Entrar</a></li>
                <li><a href="#">Matricule-se</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <!-- Conteúdo principal -->
    </main>
    <footer>
        <!-- Conteúdo do footer -->
    </footer>
</body>
</html>
```

O próximo passo seria fazer o aprofundamento de outra tag e assim por diante. Lembre-se de que essa é apenas
uma recomendação!
