# Site mobile ou mesmo site?

O volume de usuários que acessam a Internet por meio de dispositivos móveis cresceu
exponencialmente nos últimos anos. Usuários de iPhones, iPads e outros _smartphones_ e
tablets têm demandas diferentes dos usuários desktop. Pois estes dispositivos muitas vezes estão conectados em uma rede móvel com dados transmitidos via 3G ou 4G, este tipo de conexão muitas vezes apresenta instabilidade na velocidade de carregamento de dados e arquivos. Além disso é preciso se preocupar com a acessibilidade para pessoas com deficiência, que também usam este tipo de dispositivo no dia a dia, como seus recursos de comando de voz, e tela _touchscreen_ que suporta diferentes tipos de gestos com os dedos, ativando funcionalidades do _smartphones_.  

**Como atender a esses usuários?**

Para que suportemos usuários móveis, antes de tudo, precisamos tomar uma decisão: fazer um
site exclusivo - e diferente - focado em dispositivos móveis ou adaptar nosso site para
funcionar em qualquer dispositivo?  

Vários sites na internet adotam a estratégia de ter um site diferente voltado para dispositivos móveis usando um subdomínio diferente como "m." ou "mobile.", como https://m.kabum.com.br.

Essa abordagem é a que traz maior facilidade na hora de pensar nas capacidades de cada
plataforma, desktop e mobile, permitindo que entreguemos uma experiência customizada e
otimizada para cada situação. Porém, há diversos problemas envolvidos nesta escolha:

* Como atender adequadamente diversos dispositivos tão diferentes quanto um _smartphone_ com tela pequena e um tablet com tela mediana? E se ainda considerarmos as SmartTVs, ChromeCast, AppleTV? Teríamos que montar um site específico para cada tipo de plataforma?

* Muitas vezes esses sites mobile são versões limitadas dos sites de verdade e não apenas ajustes de usabilidade para o dispositivo diferente. Isso frustra a pessoa que usa onde, cada vez mais, usa dispositivos móveis para completar as mesmas tarefas que antes fazia no desktop.

* Dar manutenção em um site já é bastante trabalhoso, imagine dar manutenção em dois.

* Você terá conteúdos duplicados entre sites "diferentes", podendo prejudicar seu SEO (otimização para motores de busca) se não for feito com o cuidado que as recomendações para este cenário pedem.

* Terá que lidar com redirecionamento entre URLs móveis e normais, dependendo do dispositivo. Como por exemplo, se uma pessoa receber um link de uma página com o endereço do site desktop, e abrir no celular, terá ser redirecionada automaticamente para a versão mobile. E a mesma coisa no sentido contrário, ao abrir um link do endereço mobile em um computador ou tela grande, deverá ser redirecionado para a URL normal.

Uma abordagem que costuma ser muito utilizada é a de ter um único site, acessível em
todos os dispositivos móveis. Adeptos da ideia da Web única (**One Web**) consideram que
o melhor para o usuário é ter o mesmo site do desktop normal também acessível no mundo
móvel. É o melhor também para quem desenvolve, que não precisará manter vários sites
diferentes. E é o que garante a compatibilidade com a maior variedades de dispositivos.

Certamente, a ideia não é fazer o acesso ao site mobile exatamente da mesma
maneira que o desktop. Usando as tecnologias do CSS3, hoje já muito bem suportadas pelos navegadores, podemos
usar a mesma base de layout e marcação porém ajustando o design para cada tipo de
dispositivo.

> Hoje em dia não existe tanto essa crença de que o site precisa ser exatamente a mesma experiência do que no desktop. Podemos criar experiências exclusivas para cada tipo de dispositivo, mas é importante que o usuário ainda consiga fazer as funções (por exemplo realizar uma compra).

> **Como desenvolver um site exclusivo para Mobile?**
>
> Do ponto de vista de código, é a abordagem mais simples: basta fazer sua página com design
> mais enxuto e levando em conta que a tela será pequena (em geral, usa-se width de 100%
> para que se adapte à pequenas variações de tamanhos de telas entre _smartphones_
> diferentes).
>
> Uma dificuldade estará no servidor para detectar se o usuário está vindo de um dispositivo
> móvel ou não, e redirecioná-lo para o lugar certo. Isso costuma envolver código no
> servidor que detecte o navegador do usuário através do User-Agent do navegador.
>
> É uma boa prática também incluir um link para a versão normal do site caso o usuário não
> queira a versão móvel.




## CSS media types

Desde a época do CSS2, há uma preocupação com o suporte de regras de layout diferentes
para cada situação possível. Isso é feito usando os chamados _media types_, que podem
ser declarados na tag link do HTML através do atributo `media`:

**HTML:**  
``` html
<link rel="stylesheet" href="site.css" media="screen">
<link rel="stylesheet" href="print.css" media="print">
<link rel="stylesheet" href="handheld.css" media="handheld">
```

Outra forma de declarar os _media types_ é separar as regras dentro do próprio arquivo CSS usando a notação `@media`:

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

O _media type screen_ determina a visualização padrão, que é uma tela digital (monitores de computador ou telas de _smarthphones_). É muito comum
também termos um CSS com _media type print_ com regras de impressão (por exemplo,
retirar navegação, formatar cores para serem mais adequadas para leitura em papel etc).

E havia também o _media type handheld_, voltado para dispositivos móveis. Com ele,
conseguíamos adaptar o site para os pequenos dispositivos como celulares tipo WAP e _palmtops_.

O problema é que esse tipo _handheld_ nasceu em uma época em que os celulares eram bem
mais simples do que hoje, principalmente seus visores ou telas, portanto, costumavam ser usados para fazer visualização das páginas de maneira bem simples. 
Quando os novos _smartphones touchscreen_ começaram a surgir - em especial, o
iPhone -, eles tinham capacidade para abrir páginas completas e tão complexas quanto as do
desktop, devido a sua tela digital avançada. Por isso, o iPhone e outros celulares modernos ignoram as regras de _handheld_ e acabam por se encaixar na categoria _media type screen_.

Além disso, mesmo que _handheld_ funcionasse nos _smartphones_, como trataríamos os
diferentes dispositivos de hoje em dia como tablets, televisões etc?

A solução veio com o CSS3 e seus _**media queries**_.

## CSS3 media queries

Todos os _smartphones_ e navegadores modernos suportam uma nova forma de adaptar o CSS
baseado nas propriedades dos dispositivos, as **media queries** do CSS3.

Em vez de simplesmente falar que determinado CSS é para _handheld_ em geral, nós
podemos agora indicar que determinadas regras do CSS devem ser vinculadas a propriedades
do dispositivo como tamanho da tela, orientação (_landscape_ ou _portrait_) e até resolução em
**dpi** (_dots per inch_).

``` html
<link rel="stylesheet" href="base.css" media="screen">
<!-- usando media queries -->
<link rel="stylesheet" href="mobile.css" media="(max-width: 480px)">
```

Outra forma de declarar os _media queries_ é separar as regras dentro do mesmo arquivo CSS:  

``` css
@media screen {
  body {
    font-size: 16px;
  }
}

@media (max-width: 480px) {
  body {
    font-size: 1em;
  }
}
```

Repare como `@media` agora pode receber expressões complexas. No caso, estamos
indicando que queremos que as telas com largura máxima de 480px tenham uma fonte de
1em.  

Você pode testar isso apenas redimensionando seu próprio navegador desktop para um tamanho
menor que 480px.

## Viewport

Mas, se você tentar rodar nosso exemplo anterior em um iPhone ou Android de verdade, verá
que ainda estamos vendo a versão desktop da página. A regra do `max-width` parece ser
ignorada!

Na verdade, a questão é que os _smartphones_ modernos têm telas grandes e resoluções altas,
justamente para nos permitir ver mídias em alta resolução, como fotos e vídeos. As dimensões da tela de um iPhone SE por exemplo é 1280px por 720px. E existem _smartphones_ com Android que chegam ter telas com resolução 4K.

Ainda assim, a experiência desses celulares é bem diferente dos desktops. 4K em uma
tela de 4 polegadas é bem diferente de 4K em um notebook de 16 polegadas. A resolução
muda. Celulares costumam ter uma resolução em dpi bem maior que desktops.

**Como arrumar nossa página?**  

Os _smartphones_ sabem que considerar a tela como 4K não ajudará o usuário a visualizar
uma página Web otimizada para telas menores. Há então o conceito de _device-width_ que,
resumidamente, representa um número em pixels que o fabricante do aparelho considera como
mais próximo da sensação que o usuário tem ao visualizar a tela.

Nos iPhones, por exemplo, o _device-width_ é considerado como 370px, mesmo tendo uma tela
 com capacidade de exibir uma resolução bem mais alta.

Por padrão, iPhones, Androids e afins costumam considerar o tamanho da tela visível,
chamada de _viewport_ como grande o suficiente para comportar os sites desktop normais.
Por isso a nossa página foi mostrada sem _zoom_ como se estivéssemos no desktop.

A Apple criou então uma solução utilizando meta dados, que depois foi copiada pelos outros _smartphones_, que é configurar o valor que julgarmos mais adequado para o _viewport_:

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

**São 3 os elementos de um design responsivo:**  

* layout fluído usando medidas flexíveis, como porcentagens;
* _media queries_ para ajustes de design;
* uso de imagens flexíveis.

A ideia do responsivo é que a página se **adapte a diferentes condições**, em especial a diferentes resoluções. E, embora o uso de porcentagens exista há décadas na Web, foi a popularização das _media queries_ que permitiram layouts verdadeiramente adaptativos.

## Mobile-first

Nossos exercícios seguiram o processo que chamamos de _"desktop-first"_. Isso significa que
tínhamos nossa página montada para o layout desktop e, num segundo momento, precisaremos escrever a adaptação a mobile.

Na prática, isso não é muito interessante porque precisamos **desfazer** algumas
coisas do que tínhamos feito no nosso layout para desktop: tiramos alguns posicionamentos
e desfizemos diversos ajustes na largura de elementos que já eram padrões deles.

É muito mais comum e recomendado o uso da prática inversa: o **Mobile-first**. Isto é,
começar o desenvolvimento pelo mobile e, depois, adicionar suporte a layouts desktop.
No código, não há nenhum segredo: vamos apenas usar mais _media queries_ **min-width**
ao invés de **max-width**, mais comum em códigos desktop-first.

A grande mudança do mobile-first é que ela permite uma abordagem muito mais simples e
evolutiva/incremental. Inicia-se o desenvolvimento pela área mais simples e limitada, com mais
restrições, o mobile. O uso da tela pequena vai nos forçar a criar páginas mais simples,
focadas e objetivas. Depois, a adaptação pra desktop com _media queries_, é apenas uma questão
de readaptar o layout.

A abordagem desktop-first começa pelo ambiente mais livre e vai tentando cortar coisas quando
chega no mobile. Esse tipo de adaptação é, na prática, muito mais trabalhosa.
