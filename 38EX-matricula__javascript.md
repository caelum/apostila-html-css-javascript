# Exercício: Calculando total de horas e cursos com JavaScript

## Objetivo
      
Primeiro precisamos criar as classes com o padrão visto em aula para indicar quem queremos manipular com o JavaScript. Queremos manipular o contador de cursos, o total de horas e o botão que vai fazer a matrícula do usuário nos cursos. Depois precisamos selecionar esses elementos no arquivo JS e guarda-los em variáveis.

Agora devemos criar a função que vai cuidar da soma dos contadores e também de mostrar essa soma nos respectivos contadores da tabela. Não esquecendo de chamar essa função toda vez que um input é selecionado e a soma só pode acontecer quando o input estiver selecionado.

## Passo a passo com código

1. Crie o arquivo **`matricula.js`** na pasta **`js`** com o seguinte código:

    ###### # js/matricula.js
    ```js
    +var $tdTotalCursos = document.querySelector('.js-total-de-cursos')
    +var $tdTotalDeHoras = document.querySelector('.js-total-de-horas')
    +var $buttonConfirmar = document.querySelector('.js-botao-matricula')
    +
    +var totalHoras = 0
    +var totalCursos = 0
    +
    +
    +function adicionaCurso(checkbox){
    +  
    +  if(checkbox.checked){
    +    totalCursos ++
    +    totalHoras += parseInt(checkbox.value)
    +  }
    +  else {
    +    totalCursos --
    +    totalHoras -= parseInt(checkbox.value)
    +  }
    +  
    +  $tdTotalDeHoras.textContent = totalHoras + 'h'
    +  $tdTotalCursos.textContent = totalCursos + ' curso(s)'
    +  
    +}
    +
    +$buttonConfirmar.onclick = confirmaMatriculas
    +
    +function confirmaMatriculas() {
    +  if(totalCursos === 0) {
    +    alert('Nenhum curso selecionado')
    +  } else {
    +    alert('Matricula confirmada nos cursos!')
    +    window.location.href = 'index.html'
    +  }
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
             <table class="table table-hover rounded-top">
                 <thead class="thead-dark">
                     <tr>
                         <th scope="col"></th>
                         <th scope="col">Curso</th>
                         <th scope="col">Tempo</th>
                     </tr>
                 </thead>
                 <tbody>
                     <tr>
    -                    <̶t̶d̶>̶<̶i̶n̶p̶u̶t̶ t̶y̶p̶e̶=̶"̶c̶h̶e̶c̶k̶b̶o̶x̶"̶ n̶a̶m̶e̶=̶"̶c̶u̶r̶s̶o̶"̶ v̶a̶l̶u̶e̶=̶"̶2̶0̶"̶>̶<̶/̶t̶d̶>̶
    +                    <td><input onclick="adicionaCurso(this)" type="checkbox" name="curso" value="20"></td>
                         <td>Curso de Violão</td>
                         <td>20h</td>
                     </tr>
                     <tr>
    -                    <̶t̶d̶>̶<̶i̶n̶p̶u̶t̶ t̶y̶p̶e̶=̶"̶c̶h̶e̶c̶k̶b̶o̶x̶"̶ n̶a̶m̶e̶=̶"̶c̶u̶r̶s̶o̶"̶ v̶a̶l̶u̶e̶=̶"̶3̶0̶"̶>̶<̶/̶t̶d̶>̶
    +                    <td><input onclick="adicionaCurso(this)" type="checkbox" name="curso" value="30"></td>
                         <td>Curso de Bambolê</td>
                         <td>30h</td>
                     </tr>
                     <tr>
    -                    <̶t̶d̶>̶<̶i̶n̶p̶u̶t̶ t̶y̶p̶e̶=̶"̶c̶h̶e̶c̶k̶b̶o̶x̶"̶ n̶a̶m̶e̶=̶"̶c̶u̶r̶s̶o̶"̶ v̶a̶l̶u̶e̶=̶"̶1̶2̶"̶>̶<̶/̶t̶d̶>̶
    +                    <td><input onclick="adicionaCurso(this)" type="checkbox" name="curso" value="12"></td>
                         <td>Curso de Java</td>
                         <td>12h</td>
                     </tr>
                     <tr>
    -                    <̶t̶d̶>̶<̶i̶n̶p̶u̶t̶ t̶y̶p̶e̶=̶"̶c̶h̶e̶c̶k̶b̶o̶x̶"̶ n̶a̶m̶e̶=̶"̶c̶u̶r̶s̶o̶"̶ v̶a̶l̶u̶e̶=̶"̶2̶0̶"̶>̶<̶/̶t̶d̶>̶
    +                    <td><input onclick="adicionaCurso(this)" type="checkbox" name="curso" value="20"></td>
                         <td>Curso de Violão</td>
                         <td>20h</td>
                     </tr>
                     <tr>
    -                    <̶t̶d̶>̶<̶i̶n̶p̶u̶t̶ t̶y̶p̶e̶=̶"̶c̶h̶e̶c̶k̶b̶o̶x̶"̶ n̶a̶m̶e̶=̶"̶c̶u̶r̶s̶o̶"̶ v̶a̶l̶u̶e̶=̶"̶3̶0̶"̶>̶<̶/̶t̶d̶>̶
    +                    <td><input onclick="adicionaCurso(this)" type="checkbox" name="curso" value="30"></td>
                         <td>Curso de Bambolê</td>
                         <td>30h</td>
                     </tr>
                     <tr>
    -                    <̶t̶d̶>̶<̶i̶n̶p̶u̶t̶ t̶y̶p̶e̶=̶"̶c̶h̶e̶c̶k̶b̶o̶x̶"̶ n̶a̶m̶e̶=̶"̶c̶u̶r̶s̶o̶"̶ v̶a̶l̶u̶e̶=̶"̶1̶2̶"̶>̶<̶/̶t̶d̶>̶
    +                    <td><input onclick="adicionaCurso(this)" type="checkbox" name="curso" value="12"></td>
                         <td>Curso de Java</td>
                         <td>12h</td>
                     </tr>
                     <tr>
    -                    <̶t̶d̶>̶<̶i̶n̶p̶u̶t̶ t̶y̶p̶e̶=̶"̶c̶h̶e̶c̶k̶b̶o̶x̶"̶ n̶a̶m̶e̶=̶"̶c̶u̶r̶s̶o̶"̶ v̶a̶l̶u̶e̶=̶"̶2̶0̶"̶>̶<̶/̶t̶d̶>̶
    +                    <td><input onclick="adicionaCurso(this)" type="checkbox" name="curso" value="20"></td>
                         <td>Curso de Violão</td>
                         <td>20h</td>
                     </tr>
                     <tr>
    -                    <̶t̶d̶>̶<̶i̶n̶p̶u̶t̶ t̶y̶p̶e̶=̶"̶c̶h̶e̶c̶k̶b̶o̶x̶"̶ n̶a̶m̶e̶=̶"̶c̶u̶r̶s̶o̶"̶ v̶a̶l̶u̶e̶=̶"̶3̶0̶"̶>̶<̶/̶t̶d̶>̶
    +                    <td><input onclick="adicionaCurso(this)" type="checkbox" name="curso" value="30"></td>
                         <td>Curso de Bambolê</td>
                         <td>30h</td>
                     </tr>
                     <tr>
    -                    <̶t̶d̶>̶<̶i̶n̶p̶u̶t̶ t̶y̶p̶e̶=̶"̶c̶h̶e̶c̶k̶b̶o̶x̶"̶ n̶a̶m̶e̶=̶"̶c̶u̶r̶s̶o̶"̶ v̶a̶l̶u̶e̶=̶"̶1̶2̶"̶>̶<̶/̶t̶d̶>̶
    +                    <td><input onclick="adicionaCurso(this)" type="checkbox" name="curso" value="12"></td>
                         <td>Curso de Java</td>
                         <td>12h</td>
                     </tr>
                     <tr>
    -                    <̶t̶d̶>̶<̶i̶n̶p̶u̶t̶ t̶y̶p̶e̶=̶"̶c̶h̶e̶c̶k̶b̶o̶x̶"̶ n̶a̶m̶e̶=̶"̶c̶u̶r̶s̶o̶"̶ v̶a̶l̶u̶e̶=̶"̶2̶0̶"̶>̶<̶/̶t̶d̶>̶
    +                    <td><input onclick="adicionaCurso(this)" type="checkbox" name="curso" value="20"></td>
                         <td>Curso de Violão</td>
                         <td>20h</td>
                     </tr>
                     <tr>
    -                    <̶t̶d̶>̶<̶i̶n̶p̶u̶t̶ t̶y̶p̶e̶=̶"̶c̶h̶e̶c̶k̶b̶o̶x̶"̶ n̶a̶m̶e̶=̶"̶c̶u̶r̶s̶o̶"̶ v̶a̶l̶u̶e̶=̶"̶3̶0̶"̶>̶<̶/̶t̶d̶>̶
    +                    <td><input onclick="adicionaCurso(this)" type="checkbox" name="curso" value="30"></td>
                         <td>Curso de Bambolê</td>
                         <td>30h</td>
                     </tr>
                     <tr>
    -                    <̶t̶d̶>̶<̶i̶n̶p̶u̶t̶ t̶y̶p̶e̶=̶"̶c̶h̶e̶c̶k̶b̶o̶x̶"̶ n̶a̶m̶e̶=̶"̶c̶u̶r̶s̶o̶"̶ v̶a̶l̶u̶e̶=̶"̶1̶2̶"̶>̶<̶/̶t̶d̶>̶
    +                    <td><input onclick="adicionaCurso(this)" type="checkbox" name="curso" value="12"></td>
                         <td>Curso de Java</td>
                         <td>12h</td>
                     </tr>
                     <tr class="bg-dark text-light">
                         <td>Total</td>
                         <td class="js-total-de-cursos">0 curso(s)</td>
                         <td class="js-total-de-horas">0h</td>
                     </tr>
                 </tbody>
             </table>
    -        <̶b̶u̶t̶t̶o̶n̶ t̶y̶p̶e̶=̶"̶b̶u̶t̶t̶o̶n̶"̶ c̶l̶a̶s̶s̶=̶"̶b̶t̶n̶ b̶t̶n̶-̶o̶u̶t̶l̶i̶n̶e̶-̶d̶a̶r̶k̶ b̶t̶n̶-̶l̶g̶ m̶b̶-̶4̶"̶>̶C̶o̶n̶f̶i̶r̶m̶a̶r̶ M̶a̶t̶r̶í̶c̶u̶l̶a̶<̶/̶b̶u̶t̶t̶o̶n̶>̶
    +        <button type="button" class="js-botao-matricula btn btn-outline-dark btn-lg mb-4">Confirmar Matrícula</button>
         </main>
         <script src="js/jquery.js"></script>
         <script src="js/bootstrap.js"></script>
    +    <script src="js/matricula.js"></script>
     </body>
     </html>
    ```
