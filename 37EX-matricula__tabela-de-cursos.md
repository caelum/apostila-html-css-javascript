# Exercício: A tabela de cursos

## Objetivo
      
Construa a estrutura de uma tabela contendo 3 informações no cabeçalho:

    - (espaço vazio)
    - Nome do curso
    - Tempo/Carga Horária

No corpo da tabela coloque na primeira coluna um ```<input>``` do tipo ```checkbox``` com o valor do tempo/carga horária. Na segunda coluna coloque o nome de algum curso e na terceira coluna coloque o valor em horas do tempo/carga horária.

Não esqueça de colocar as classes como na documentação do Bootstrap

## Passo a passo com código

1. No arquivo **`matricula.css`** na pasta **`css`** faça as seguintes alterações:

    ###### # css/matricula.css
    ```css
     .header-navbar-logo {
         width: 8rem;
         margin-right: 1rem;
     }
     
     .header-matricula h1 {
         font-weight: 300;
     }
    +
    +.rounded-top {
    +    overflow: hidden;
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
         <link href="css/matricula.css" rel="stylesheet">
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
             <div class="jumbotron bg-dark header-matricula text-light mt-3">
                 <div class="container">
                     <h1>Escolher cursos</h1>
                     <p class="lead">Escolha os cursos que gostaria de se matricular</p>
                 </div>
             </div>
    +        <table class="table table-hover rounded-top">
    +            <thead class="thead-dark">
    +                <tr>
    +                    <th scope="col"></th>
    +                    <th scope="col">Curso</th>
    +                    <th scope="col">Tempo</th>
    +                </tr>
    +            </thead>
    +            <tbody>
    +                <tr>
    +                    <td><input type="checkbox" name="curso" value="20"></td>
    +                    <td>Curso de Violão</td>
    +                    <td>20h</td>
    +                </tr>
    +                <tr>
    +                    <td><input type="checkbox" name="curso" value="30"></td>
    +                    <td>Curso de Bambolê</td>
    +                    <td>30h</td>
    +                </tr>
    +                <tr>
    +                    <td><input type="checkbox" name="curso" value="12"></td>
    +                    <td>Curso de Java</td>
    +                    <td>12h</td>
    +                </tr>
    +                <tr>
    +                    <td><input type="checkbox" name="curso" value="20"></td>
    +                    <td>Curso de Violão</td>
    +                    <td>20h</td>
    +                </tr>
    +                <tr>
    +                    <td><input type="checkbox" name="curso" value="30"></td>
    +                    <td>Curso de Bambolê</td>
    +                    <td>30h</td>
    +                </tr>
    +                <tr>
    +                    <td><input type="checkbox" name="curso" value="12"></td>
    +                    <td>Curso de Java</td>
    +                    <td>12h</td>
    +                </tr>
    +                <tr>
    +                    <td><input type="checkbox" name="curso" value="20"></td>
    +                    <td>Curso de Violão</td>
    +                    <td>20h</td>
    +                </tr>
    +                <tr>
    +                    <td><input type="checkbox" name="curso" value="30"></td>
    +                    <td>Curso de Bambolê</td>
    +                    <td>30h</td>
    +                </tr>
    +                <tr>
    +                    <td><input type="checkbox" name="curso" value="12"></td>
    +                    <td>Curso de Java</td>
    +                    <td>12h</td>
    +                </tr>
    +                <tr>
    +                    <td><input type="checkbox" name="curso" value="20"></td>
    +                    <td>Curso de Violão</td>
    +                    <td>20h</td>
    +                </tr>
    +                <tr>
    +                    <td><input type="checkbox" name="curso" value="30"></td>
    +                    <td>Curso de Bambolê</td>
    +                    <td>30h</td>
    +                </tr>
    +                <tr>
    +                    <td><input type="checkbox" name="curso" value="12"></td>
    +                    <td>Curso de Java</td>
    +                    <td>12h</td>
    +                </tr>
    +                <tr class="bg-dark text-light">
    +                    <td>Total</td>
    +                    <td class="js-total-de-cursos">0 curso(s)</td>
    +                    <td class="js-total-de-horas">0h</td>
    +                </tr>
    +            </tbody>
    +        </table>
    +        <button type="button" class="btn btn-outline-dark btn-lg mb-4">Confirmar Matrícula</button>
         </main>
         <script src="js/jquery.js"></script>
         <script src="js/bootstrap.js"></script>
     </body>
     </html>
    ```
