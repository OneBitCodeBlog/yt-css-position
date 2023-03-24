# Dominando a propriedade position do CSS

E aí, programador(a)! Tudo bem?

O posicionamento de elementos na interface é uma peça fundamental do front-end, mas hoje quando falamos de posicionamento é muito comum pularmos imediatamente para assuntos como flex e grid, deixando para trás uma das propriedades mais importantes e úteis do CSS, a *position*.

## Lembrete importante

Mas antes de falar da position, existe um conceito muito importante que você precisa se lembrar bem para entendê-la, o fluxo do documento HTML. Por padrão os elementos em um documento HTML seguem um fluxo padrão, indo do topo para o fundo em blocos e da esquerda para a direita em elementos inline, ou seja, todos os elemento HTML vão sendo colocados nessa ordem e ocupando o espaço necessário para serem exibidos, com os elementos seguintes sendo posicionados abaixo do anterior. Com esse fluxo de posicionamento padrão em mente, vamos à position.

## Entendendo a position

Existem 5 tipos de position no CSS:

- **static**: o valor padrão, qualquer elemento que não receber um valor diferente de position será estático. Esse valor indica que o elemento deverá ser estático no fluxo do documento HTML, não sendo afetado pelas propriedades top, right, bottom e left.
- **relative**: bem parecido com o static, o relative faz com que o elemento continue inserido no fluxo do documento HTML, mas permite posicioná-lo usando as propriedades top, right, bottom e left. Isso irá preservar a área original do elemento no fluxo do documento e calculará o seu posicionamento usando como referência essa área original.
- **absolute**: como o próprio nome diz, irá posicionar o elemento de forma absoluta, ou seja, completamente fora do fluxo do documento. Além disso, as propriedades top, right, bottom e left serão calculadas usando como referência o próprio corpo do documento ou o primeiro elemento pai que tenha uma position diferente de static (como o relative, por exemplo).
- **fixed**: semelhante ao absolute, mas com um detalhe crucial: o posicionamento do elemento ficará fixo ao rolar pela página.
- **sticky**: possivelmente o mais diferente de todos, o valor sticky (do inglês, grudento, ou que cola) irá posicionar o elemento como o relative, dentro do fluxo do documento. No entanto, ao rolar pela página o suficiente para que ele saia da viewport, seu posicionamento muda e ele passa a ficar “grudado” dentro dela, impedindo que ele saia para fora da área de exibição.

## Propriedades de posicionamento

Como você deve ter percebido, as propriedades top, right, bottom e left são muito importantes quando usamos a position, afinal são elas que, de fato, posicionam o elemento de acordo com o seu tipo de posicionamento. Sendo assim, é bem importante entender como elas funcionam:

- as propriedades **top**, **right**, **bottom** e **left** servem para “empurrar” ou “puxar” o elemento para as quatro direções, cima, direita, baixo e esquerda, respectivamente.
- as quatro aceitam as medidas comuns do CSS: px, %, rem, em, etc.
- as quatro funcionam “de fora para dentro” do documento, ou seja, valores positivos em qualquer uma delas irão “empurrar” o elemento a partir daquela direção para dentro do documento, enquanto valores negativos irão “puxar” o elemento daquela direção para fora.
- Por exemplo: a propriedade `left: 100px;` em um elemento irá empurrá-lo da esquerda para dentro do documento e `left: -100px;` irá empurrar da esquerda para fora.