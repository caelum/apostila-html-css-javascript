# Exercício: Customizando o Bootstrap (opicional)

## Objetivo
      
Crie um novo arquivo css que irá conter as mudanças do peso da fonte do título do jumbotron para ```600``` e a largura da imagem para ```8rem``` e um espaçamento externo à direta da imagem de ```1rem```. Não esqueça de criar classes para esses elementos.

## Passo a passo com código

1. Crie o arquivo **`matricula.css`** na pasta **`css`** com o seguinte código:

    ###### # css/matricula.css
    ```css
    +.header-navbar-logo {
    +    width: 8rem;
    +    margin-right: 1rem;
    +}
    +
    +.header-matricula h1 {
    +    font-weight: 300;
    +}
    ```

2. No arquivo **`matricula.html`** na pasta **`raíz do projeto`** faça as seguintes alterações:

    ###### # matricula.html
    ```html
     <!DOCTYPE html>
     <html>
     <head>
         <title>Matriculas</title>
         <meta charset="utf-8">
         <meta name="viewport" content="width=device-width">
         <link href="css/bootstrap.css" rel="stylesheet">
    +    <link href="css/matricula.css" rel="stylesheet">
         <link href="img/favicon.ico" rel="icon">
     </head>
     <body>
         <header class="header">
             <nav class="navbar navbar-expand-sm navbar-dark bg-dark">
                 <a class="navbar-brand" href="index.html"><img class="header-navbar-logo" src="img/musicdot-logo-light.svg" alt="Logo da Musicdot"></a>
                 <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                     <span class="navbar-toggler-icon"></span>
                 </button>
                 <div class="collapse navbar-collapse" id="navbarSupportedContent">
                     <ul class="navbar-nav mr-auto">
                         <li class="nav-item active">
                             <a class="nav-link" href="#">Cursos</a>
                         </li>
                         <li class="nav-item">
                             <a class="nav-link" href="#">Matriculas</a>
                         </li>
                         <li class="nav-item">
                             <a href="#" class="nav-link">Emails</a>
                         </li>
                     </ul>
                 </div>
             </nav>
         </header>
         <main class="container mb-4">
    -        <̶d̶i̶v̶ c̶l̶a̶s̶s̶=̶"̶j̶u̶m̶b̶o̶t̶r̶o̶n̶ b̶g̶-̶d̶a̶r̶k̶ t̶e̶x̶t̶-̶l̶i̶g̶h̶t̶ m̶t̶-̶3̶"̶>̶
    +        <div class="jumbotron bg-dark header-matricula text-light mt-3">
                 <div class="container">
                     <h1>Escolher cursos</h1>
                     <p class="lead">Escolha os cursos que gostaria de se matricular</p>
                 </div>
             </div>
         </main>
         <script src="js/jquery.js"></script>
         <script src="js/bootstrap.js"></script>
     </body>
     </html>
    ```
