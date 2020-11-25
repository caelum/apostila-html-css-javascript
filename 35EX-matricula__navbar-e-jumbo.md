# Exercício: Primeiros passos com Bootstrap

## Objetivo
      
Para começar a usar o Bootstrap primeiro importe três arquivos importantes:
    
    - bootstrap.css
    - jquery.js
    - bootstrap.js

Depois abra a documentação do Bootstrap e procure pela estrutura exemplo de um header. Modifique para que o header contenha a logo da musicdot e que possua três links: 

    - Cursos
    - Matrículas
    - Email

Dentro da tag `<main>` crie a estrutura de um Jumbotron e, assim como no header, modifique-o para que fique com os textos certos. No título do Jumbotron: "Escolher cursos" e no parágrafo abaixo do título: "Escolha os cursos que gostaria de se matricular". Para estilizar toda a página utilize as classes css necessárias que estão na documentação do Bootstrap.

## Passo a passo com código

1. Crie o arquivo **`matricula.html`** na pasta **`raíz do projeto`** com o seguinte código:

    ###### # matricula.html
    ```html
    +<!DOCTYPE html>
    +<html>
    +<head>
    +    <title>Matriculas</title>
    +    <meta charset="utf-8">
    +    <meta name="viewport" content="width=device-width">
    +    <link href="css/bootstrap.css" rel="stylesheet">
    +    <link href="img/favicon.ico" rel="icon">
    +</head>
    +<body>
    +    <header class="header">
    +        <nav class="navbar navbar-expand-sm navbar-dark bg-dark">
    +            <a class="navbar-brand" href="index.html"><img class="header-navbar-logo" src="img/musicdot-logo-light.svg" alt="Logo da Musicdot"></a>
    +            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    +                <span class="navbar-toggler-icon"></span>
    +            </button>
    +            <div class="collapse navbar-collapse" id="navbarSupportedContent">
    +                <ul class="navbar-nav mr-auto">
    +                    <li class="nav-item active">
    +                        <a class="nav-link" href="#">Cursos</a>
    +                    </li>
    +                    <li class="nav-item">
    +                        <a class="nav-link" href="#">Matriculas</a>
    +                    </li>
    +                    <li class="nav-item">
    +                        <a href="#" class="nav-link">Emails</a>
    +                    </li>
    +                </ul>
    +            </div>
    +        </nav>
    +    </header>
    +    <main class="container mb-4">
    +        <div class="jumbotron bg-dark text-light mt-3">
    +            <div class="container">
    +                <h1>Escolher cursos</h1>
    +                <p class="lead">Escolha os cursos que gostaria de se matricular</p>
    +            </div>
    +        </div>
    +    </main>
    +    <script src="js/jquery.js"></script>
    +    <script src="js/bootstrap.js"></script>
    +</body>
    +</html>
    ```
