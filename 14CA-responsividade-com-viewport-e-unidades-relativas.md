# Site mobile ou mesmo site?

O volume de usuários que acessam a internet por meio de dispositivos móveis cresceu
exponencialmente nos últimos anos. Usuários de iPhones, iPads e outros smartphones e
tablets têm demandas diferentes dos usuários Desktop. Redes nem sempre rápidas e acessibilidade em dispositivos limitados e multitoque são as principais diferenças.

Como atender a esses usuários?

Para que suportemos usuários móveis, antes de tudo, precisamos tomar uma decisão: fazer um
site exclusivo - e diferente - focado em dispositivos móveis ou adaptar nosso site para
funcionar em qualquer dispositivo?

Vários sites na internet adotam a estratégia de ter um site diferente voltado para dispositivos móveis usando um subdomínio diferente como "m." ou "mobile.", como https://m.kabum.com.br.

Essa abordagem é a que traz maior facilidade na hora de pensar nas capacidades de cada
plataforma, Desktop e mobile, permitindo que entreguemos uma experiência customizada e
otimizada para cada situação. Porém, há diversos problemas envolvidos:


* Como atender adequadamente diversos dispositivos tão diferentes quanto um smartphone com
tela pequena e um tablet com tela mediana? E se ainda considerarmos as SmartTVs, ChromeCast, AppleTV? Teríamos que montar um site específico para cada tipo de plataforma?

* Muitas vezes esses sites mobile são versões limitadas dos sites de verdade e não apenas
ajustes de usabilidade para o dispositivo diferente. Isso frustra o usuário que,
cada vez mais, usa dispositivos móveis para completar as mesmas tarefas que antes fazia no
Desktop.

* Dar manutenção em um site já é bastante trabalhoso, imagine dar manutenção em dois.

* Você terá conteúdos duplicados entre sites "diferentes", podendo prejudicar seu SEO se
não for feito com cuidado.

* Terá que lidar com redirects entre URLs móveis e normais, dependendo do dispositivo. O
usuário pode receber de um amigo um link para uma página vista no site normal, mas se ele
abrir esse email no celular, terá que ver a versão mobile desse link, sendo redirecionado
automaticamente. E a mesma coisa no sentido contrário, ao mandar um link de volta para o
Desktop.


Uma abordagem que costumas ser muito utilizada é a de ter um único site, acessível em
todos os dispositivos móveis. Adeptos da ideia da Web única (**One Web**) consideram que
o melhor para o usuário é ter o mesmo site do Desktop normal também acessível no mundo
móvel. É o melhor para o desenvolvedor também, que não precisará manter vários sites
diferentes. E é o que garante a compatibilidade com a maior gama de aparelhos diferentes.

Certamente, a ideia não é fazer o usuário móvel acessar a página exatamente da mesma
maneira que o usuário Desktop. Usando truques de CSS3 bem suportados no mercado, podemos
usar a mesma base de layout e marcação porém ajustando o design para cada tipo de
dispositivo.

> Hoje em dia não existe tanto essa crença de que o site precisa ser exatamente a mesma experiência do que no Desktop. Podemos criar experiências exclusivas para cada tipo de dispositivo, mas é importante que o usuário ainda consiga fazer as funções (por exemplo realizar uma compra).


> **Como desenvolver um site exclusivo para Mobile?**
>
>
> Do ponto de vista de código, é a abordagem mais simples: basta fazer sua página com design
> mais enxuto e levando em conta que a tela será pequena (em geral, usa-se width de 100%
> para que se adapte à pequenas variações de tamanhos de telas entre smartphones
> diferentes).
>
> Uma dificuldade estará no servidor para detectar se o usuário está vindo de um dispositivo
> móvel ou não, e redirecioná-lo para o lugar certo. Isso costuma envolver código no
> servidor que detecte o navegador do usuário usando o User-Agent do navegador.
>
> É uma boa prática também incluir um link para a versão normal do site caso o usuário não
> queira a versão móvel.




## CSS media types

Desde a época do CSS2, há uma preocupação com o suporte de regras de layout diferentes
para cada situação possível. Isso é feito usando os chamados _media types_, que podem
ser declarados ao se invocar um arquivo CSS:

``` html
<link rel="stylesheet" href="site.css" media="screen">
<link rel="stylesheet" href="print.css" media="print">
<link rel="stylesheet" href="handheld.css" media="handheld">
```

Outra forma de declarar os _media types_ é separar as regras dentro do próprio arquivo CSS:

``` css
@media screen {
  body {
    background-color: blue;
    color: white;
  }
}

@media print {
  body {
    background-color: white;
    color: black;
  }
}
```

O _media type screen_ determina a visualização normal, na tela do Desktop. É muito comum
também termos um CSS com _media type print_ com regras de impressão (por exemplo,
retirar navegação, formatar cores para serem mais adequadas para leitura em papel etc).

E havia também o _media type handheld_, voltado para dispositivos móveis. Com ele,
conseguíamos adaptar o site para os pequenos dispositivos como celulares WAP e palmtops.

O problema é que esse tipo _handheld_ nasceu em uma época em que os celulares eram bem
mais simples do que hoje, e, portanto, costumavam ser usados para fazer páginas bem
simples. Quando os novos smartphones _touchscreen_ começaram a surgir - em especial, o
iPhone -, eles tinham capacidade para abrir páginas completas e tão complexas quanto as do
Desktop. Por isso, o iPhone e outros celulares modernos ignoram as regras de _handheld_
e se consideram, na verdade, _screen_.

Além disso, mesmo que _handheld_ funcionasse nos smartphones, como trataríamos os
diferentes dispositivos de hoje em dia como tablets, televisões etc?

A solução veio com o CSS3 e seus _media queries_.

## CSS3 media queries

Todos os smartphones e navegadores modernos suportam uma nova forma de adaptar o CSS
baseado nas propriedades dos dispositivos, as **media queries** do CSS3.

Em vez de simplesmente falar que determinado CSS é para _handheld_ em geral, nós
podemos agora indicar que determinadas regras do CSS devem ser vinculadas a propriedades
do dispositivo como tamanho da tela, orientação (landscape ou portrait) e até resolução em
dpi.

``` html
<link rel="stylesheet" href="base.css" media="screen">
<link rel="stylesheet" href="mobile.css" media="(max-width: 480px)">
```

Outra forma de declarar os _media types_ é separar as regras dentro do mesmo arquivo CSS:

``` css
@media screen {
  body {
    font-size: 16px;
  }
}

@media (max-width: 480px) {
  body {
    font-size: 12px;
  }
}
```

Repare como o atributo _media_ agora pode receber expressões complexas. No caso, estamos
indicando que queremos que as telas com largura máxima de 480px tenham uma fonte de
12px.

Você pode testar isso apenas redimensionando seu próprio navegador Desktop para um tamanho
menor que 480px.

## Viewport

Mas, se você tentar rodar nosso exemplo anterior em um iPhone ou Android de verdade, verá
que ainda estamos vendo a versão Desktop da página. A regra do _max-width_ parece ser
ignorada!


Na verdade, a questão é que os smartphones modernos têm telas grandes e resoluções altas,
justamente para nos permitir ver sites complexos feitos para Desktop. A tela de um iPhone
SE por exemplo é 1280px por 720px. Celulares Android já chegam a 4K.

Ainda assim, a experiência desses celulares é bem diferente dos Desktops. 4K em uma
tela de 4 polegadas é bem diferente de 4K em um notebook de 16 polegadas. A resolução
muda. Celulares costumam ter uma resolução em dpi bem maior que Desktops.

Como arrumar nossa página?

Os smartphones sabem que considerar a tela como 4K não ajudará o usuário a visualizar
a página otimizada para telas menores. Há então o conceito de _device-width_ que,
resumidamente, representa um número em pixels que o fabricante do aparelho considera como
mais próximo da sensação que o usuário tem ao visualizar a tela.

Nos iPhones, por exemplo, o _device-width_ é considerado como 370px, mesmo com a tela
tendo uma resolução bem mais alta.

Por padrão, iPhones, Androids e afins costumam considerar o tamanho da tela visível,
chamada de _viewport_ como grande o suficiente para comportar os sites Desktop normais.
Por isso a nossa página foi mostrada sem zoom como se estivéssemos no Desktop.

A Apple criou então uma solução que depois foi copiada pelos outros smartphones, que é
configurar o valor que julgarmos mais adequado para o _viewport_:

``` html
<meta name="viewport" content="width=370">
```

Isso faz com que a tela seja considerada com largura de 370px, fazendo com que nosso layout
mobile finalmente funcione e nossas _media queries_ também.

Melhor ainda, podemos colocar o _viewport_ com o valor `device-width` definido pelo
fabricante, dando mais flexibilidade com dispositivos diferentes com tamanhos diferentes:

``` html
<meta name="viewport" content="width=device-width">
```

## Responsive Web Design

Pequenas mudanças que fazemos usando `@media` tentando fazer a experiência do usuário em diversos dispositivos mais atraente é o que o mercado chama de **Web Design Responsivo**. O termo surgiu num famoso artigo de Ethan Marcotte e diz o seguinte:

São 3 os elementos de
um design responsivo:


* layout fluído usando medidas flexíveis, como porcentagens;
* _media queries_ para ajustes de design;
* uso de imagens flexíveis.


A ideia do responsivo é que a página se **adapte a diferentes condições**, em especial a diferentes resoluções. E, embora o uso de porcentagens exista há décadas na Web, foi a popularização das _media queries_ que permitiram layouts verdadeiramente adaptativos.

## Mobile-first

Nossos exercícios seguiram o processo que chamamos de _desktop-first_. Isso significa que
tínhamos nossa página montada para o layout Desktop e, num segundo momento, precisaremos codar a adaptação a mobile.

Na prática, isso não é muito interessante porque precisamos **desfazer** algumas
coisas do que tínhamos feito no nosso layout para desktop: tiramos alguns posicionamentos
e desfizemos diversos ajustes na largura de elementos que já eram padrões deles.

É muito mais comum e recomendado o uso da prática inversa: o **Mobile-first**. Isto é,
começar o desenvolvimento pelo mobile e, depois, adicionar suporte a layouts desktop.
No código, não há nenhum segredo: vamos apenas usar mais _media queries_ **min-width**
ao invés de **max-width**, mais comum em códigos desktop-first.

A grande mudança do mobile-first é que ela permite uma abordagem muito mais simples e
evolutiva. Inicia-se o desenvolvimento pela área mais simples e limitada, com mais
restrições, o mobile. O uso da tela pequena vai nos forçar a criar páginas mais simples,
focadas e objetivas. Depois, a adaptação pra Desktop com _media queries_, é apenas uma questão
de readaptar o layout.

A abordagem desktop-first começa pelo ambiente mais livre e vai tentando cortar coisas quando
chega no mobile. Esse tipo de adaptação é, na prática, muito mais trabalhosa.