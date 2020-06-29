# Unidades relativas com EM e REM

Já vimos em exercícios passados o uso da unidade de medida relativa com `%`. Usamos essa medida relativa quando queremos que um elemento use, por exemplo, `100%` do espaço disponível.

**HTML:**  
``` html
<div>
    <img src="img/flor.png" alt="Foto de uma flor">
</div>
```

**CSS:**  
``` css
div {
    width: 400px;
}
```

No exemplo acima, dependendo do tamanho da imagem, a imagem pode ultrapassar o espaço que definimos para a `<div>` ou pode ocupar um espaço menor. Se queremos que a imagem ocupe todo o espaço da `<div>` podemos usar a unidade relativa `%`:

``` css
div {
    width: 400px;
}

img {
    width: 100%; /* Ocupe 100% do espaço disponível */
}
```

A grande vantagem de se usar `%` é que não importa o tamanho que colocamos na `<div>`, a `<img>` sempre vai acompanhar o tamanho da sua tag mãe (a `<div>`).

**EM** e **REM** tem o mesmo conceito de `%` mas ao invés de serem baseadas no tamanho de um elemento, essas medidas são baseadas em tamanho de fonte. **EM** usa o tamanho da fonte do elemento pai e **REM** usa o tamanho da fonte do `<html>`.

**HTML:**  
``` html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Um exemplo</title>
</head>
<body>
    <div>
        <img src="img/foto" alt="Uma foto">
    </div>
</body>
</html>
```

**CSS:**  
``` css
html {
    font-size: 10px;
}

div {
    font-size: 20px;
}

img {
    width: 10em; /* A largura será de 200px */
    height: 10rem; /* A altura será de 100px */
}
```

A vantagem de usar essas medidas é que se tivermos outros elementos usando essas medidas e precisarmos mudar o tamanho de todos os elementos proporcionalmente, basta mudarmos em um lugar só. Estas unidades de medida são ideais para quando o site precisa ser exibido em diferentes tamanhos de telas, onde em cada tamanho de tela a fonte deve ser exibida em escalas de tamanhos diferentes e proporcionais entre si.
