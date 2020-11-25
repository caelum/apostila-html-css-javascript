# Responsividade e Fallback

Vamos acabar encontrando casos de incompatibilidade de propriedades CSS com os browsers que usamos. Nem todas as pessoas atualizam seus browsers, seja por não saber atualizar, por uma feature específica daquela versão, compatibilidade com o sistema operacional, etc... por conta disso, algumas propriedades CSS que usamos não vão funcionar em todos os browsers. Vimos em capítulos anteriores que o site [caniuse.com](https://caniuse.com/) mostra um gráfico falando sobre compatibilidade de propriedades CSS com diversas versões de browsers, e a idéia de usar esse site é por conta das métricas que ele nos apresenta. Uma dessas métricas é a quantidade de usuários utilizando versões diferentes de browsers. Vamos montar nosso site pensando na maioria dos usuários (que costumam usar versões mais atualizadas de browsers) mas não esquecendo das pequenas porcentagens que usam navegadores mais antigos (IE 10 por exemplo). Só que não podemos deixar de colocar novas propriedades e tags por conta da pequena porcentagem de pessoas que usam navegadores muito antigos. O que fazemos então?

Vamos ver o exemplo baixo:

```css
.meu-elemento {
    background-color: #f00;
}
```

No exemplo nós colocamos uma cor de fundo vermelha num elemento que possui a classe `meu-elemento`. Agora vamos observar o exemplo abaixo:

```css
.meu-elemento {
    background-color: #f00;
    background-color: #0f0;
}
```

Agora o navegador vai ler primeiro a cor vermelha e depois vai substituir pela cor verde porque estamos usando a mesma propriedade no mesmo elemento, ou seja, quem for declarado por último ganha a preferência. Agora vamos ver mais um exemplo.

```css
.meu-elemento {
    background-color: #f00;
    background-color: corlinda(10);
}
```

A função `corlinda()` não é um CSS válido portanto o navegador vai ler a cor vermelha primeiro e depois vai tentar ler a função, mas como essa função não existe o navegador vai ignorar a sobrescrita e vai manter a cor de fundo vermelha.

Essa é a maneira mais ideal de manter compatibilidade com browsers mais antigos. Seguindo o conceito de Progressive Enhancement, começamos a colocar nossas propriedades baseadas nos navegadores mais antigos e depois vamos crescendo para propriedades mais novas de navegadores mais novos, assim naturalmente vamos deixando nosso site responsivo e compatível com diversos navegadores.

> É importante ver que na hora de decidir qual propriedade antiga usar como "piso" da progressão, essa propriedade faça sentido para a época que o site for criado.
>
> Não vamos usar propriedades do _Internet Explorer 6_ porque já é um navegador extremamente velho e que não apresenta mais pacotes de segurança para o uso na internet. Mas podemos considerar o _Internet Explorer 11_ que ainda possui uma quantidade de usuários considerável.
