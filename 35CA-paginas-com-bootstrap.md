# Bootstrap e frameworks de CSS

Uma tendência em alta no mundo front-end é o uso de frameworks CSS com estilos base para nossa página. Ao invés de começar todo projeto do zero, criando todo estilo  na mão, existem frameworks que já trazem toda uma base construída de onde partiremos nossa aplicação.

Existem muitas opções mas o **Bootstrap** talvez seja o de maior notoriedade. Ele foi criado pelo pessoal do Twitter a partir de códigos que eles já usavam internamente. Foi liberado como opensource e ganhou muitos adeptos. O projeto cresceu bastante em maturidade e importância no mercado a ponto de se desvincular do Twitter e ser apenas o **Bootstrap**.

<https://getbootstrap.com/>

O Bootstrap traz uma série de recursos:

* Reset CSS
* Estilo visual base pra maioria das tags
* Ícones
* Grids prontos pra uso
* Componentes CSS
* Plugins JavaScript
* Tudo responsivo e mobile-first

## Estilo e componentes base

Para usar o Bootstrap, apenas incluímos seu CSS na página:

``` html
<link rel="stylesheet" href="css/bootstrap.css">
```

Só isso já nos traz uma série de benefícios. Um reset é aplicado, e nossas tags ganham estilo e tipografia base. Isso quer dizer que podemos usar tags como um H1 ou um P agora e elas terão um estilo característico do Bootstrap.

Além disso, ganhamos **muitas classes** com componentes adicionais que podemos aplicar na página. São várias opções. Por exemplo, pra criar um título com uma frase de abertura em destaque, usamos o Jumbotron:

``` html
<div class="jumbotron jumbotron-fluid">
	<div class="container">
		<h1 class="display-4">Ótima escolha!</h1>
		<p class="lead">Obrigado por comprar na Mirror Fashion.</p>
	</div>
</div>
```

O Bootstrap utiliza a idéia de reaproveitamento de classes que vimos em capítulos anteriores para estilizar páginas. No exemplo acima, para criar um componente do tipo _jumbotron_ nós só precisamos criar um elemento e chamar a classe que representa esse componente. Isso facilita muito na hora de criar páginas do zero porque se a pessoa já está acostumada com a nomenclatura e conhece bem os componentes do Bootstrap, já é possível escrever o HTML com os nomes de classes corretos. Então reduz o tempo quase que pela metade na hora de desenvolver porque não precisamos mais focar tanto em propriedades CSS e sim em estrutura. Na documentação do Bootstrap existem vários exemplos de estruturas que podemos literalmente copiar e colar e alterar para o conteúdo que precisamos.

> A recomendação para o uso do Bootstrap (principalmente para pessoas novas com o framework) é deixar uma aba aberta do navegador com a documentação para conferir os componentes, estruturas e ferramentas enquanto escreve a estrutura.

<!-- Comentário de quebra de block -->

> Podemos fazer nossa prórpria adaptação do CSS do Bootstrap. Basta sobrescrever as classes que queremos usar em um arquivo separado e fazer o import depois do CSS do Bootstrap.

Alguns componentes do Bootstrap possuem interatividade com o usuário através de JavaScript, então além de importar o arquivo CSS precisamos importar também o arquivo de javaScript. Só que para o JavaScript do Bootstrap funcionar ele precisa de um outro framework chamado _JQuery_.

<https://jquery.com/>

A importação desses JavaScripts é feita logo antes do fechamento da tag `</body>` e o import do _JQuery_ deve vir antes do arquivo do Bootstrap:

```html

...

    <script src="js/jquery.js"></script>
    <script src="js/bootstrap.js.js"></script>
</body>
</html>
```
