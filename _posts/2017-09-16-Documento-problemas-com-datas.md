---
date: 2017-09-16
title: Evitando problemas com datas
categories:
  - indices-previdenciarios
  - calculos-previdenciarios
  - desenvolvimento-de-planilhas
description: Por que você pode ter problemas com as datas em Google Sheets e o que fazer para prevenir-se.
type: Document
---
Neste tutorial explicaremos como o *Google Sheets* interpreta as datas inseridas nas planilhas e nos complementos, como e por que os cálculos com datas podem dar errado e o que se pode fazer para evitar que tais erros aconteçam.

## Como as datas são interpretadas em *Google Sheets*

Trabalhar com datas já era um desafio em *Excel* e assim permanece em *Google Sheets*. A razão disso é que os sistemas computacionais manipulam as datas de um modo muito especial, diferente dos outros tipos de valores.

Para que as datas possam ser comparadas entre si e utilizadas em fórmulas matemáticas, os computadores precisam tratá-las como números sequenciais simples. Desse modo, uma data é posterior a outra se seu número é maior, e anterior se menor. Duas datas são iguais se correspondem a um mesmo número.

Já os seres humanos utilizam no dia-a-dia uma notação bem mais complexa para expressar datas. 

Costumamos utilizar um conjunto de três números: 1) o ano, que é parte de uma sequência numérica teoricamente infinita e irrepetível, isto é, cada ano tem seu número próprio e único; 2) o mês, que é parte de uma sequência numérica cíclica, de modo que duas datas diferentes podem ter um mesmo número no mês; e 3) o dia, que se comporta de modo semelhante ao mês. 

Assim, para nós, salvo no que se refere ao ano, o fato desses números, numa data qualquer, serem maiores ou menores que os mesmos números em outra data não permite, por si, dizer qual a data posterior ou anterior. Precisamos sempre levar em conta, na comparação, os três números em conjunto. Assim, por exemplo, o dia `05/03/2015` é posterior ao dia `30/11/2014` não porque os números utilizados para representar o mês e o dia sejam maiores (porque nesse caso eles são menores na data posterior), mas apenas porque o ano é maior.

A primeira dificuldade para os sistemas computacionais reside, portanto, em “traduzir” a notação humana de modo a que ela possa ser expressa em numeração única. 

Além disso, quando lidamos com datas, quase sempre o horário é irrelevante para nós. Por exemplo, se estamos comparando duas DERs, não importa para nós o horário em que o requerimento adminstrativo foi apresentado. 

Até mesmo outros componentes das datas podem ser irrelevantes em alguns casos, como o dia do mês, por exemplo, quando comparamos duas competências.

Já os computadores nunca desconsideram nenhum dos elementos das datas e levam sempre em conta também o horário, até o último grau de precisão. Para um sistema computacional que chega à precisão de segundos, por exemplo, o requerimento formulado em `01/02/2015, às 17:01:01` será sempre posterior ao formulado em `01/02/2015, às 17:01:00`, ainda que para nós os segundos sejam irrelevantes.

Todavia, os computadores são ferramentas utilizadas por seres humanos e precisam retornar para o usuário dados que possam ser por ele compreendidos e que lhe possam ser úteis. Por isso é bastante comum que nos sistemas computacionais as datas tenham sempre “duas faces”:

1) quando utilizadas num cálculo, elas são tratadas como números sequenciais;

2) quando retornam o resultado ao usuário, elas são estruturadas de um modo mais complexo, que incorpora diversos dados diferentes, não apenas os já citados (ano, mês e dia), como também outros conceitos empregados no dia-a-dia para medição do tempo, como fuso horário, horário de verão, diferentes calendários, distinção entre horas da manhã e da tarde (“am”, “pm”) etc.

Nas planilhas do *Google Sheets*, quando as datas são utilizadas em um cálculo, elas são tratadas como um número decimal cuja parte inteira corresponde ao número de dias transcorridos desde 30/12/1899 e a parte fracionária ao horário do dia. 

Todavia, quando se trata de visualizar o resultado, o *Google Sheets* permite que o usuário estabeleça vários formatos diferentes e contempla, ainda, ajustes de fuso horário e de horário de verão.

Por exemplo, se digitamos o número `42370,92` numa célula e escolhemos exibi-lo como uma data, veremos que o referido número equivale a `01/01/2016 22:00:00`. Do mesmo modo, se digitamos numa célula a data `01/01/2016 22:00:00`, a planilha interpretará a informação como o número `42370,92`.

Já os complementos adotam um outro sistema. Sendo escritos numa linguagem chamada de *Javascript* ou *ECMAScript*, eles seguem o padrão estabelecido para essa linguagem, expressando cada instante em número de milissegundos transcorridos a partir da "[Era Unix](https://pt.wikipedia.org/wiki/Era_Unix){:target="_blank"}.

Por exemplo, o instante `2016-01-02T00:00:00.000Z`, equivalente às 22h00 do dia 01/01/2016, horário de verão brasileiro, corresponde, em *Javascript*, ao número `1451692800000`. E o número seguinte, `1451692800001`, embora represente uma diferença de apenas um milésimo de segundo em relação ao anterior, constitui, para o computador, uma data totalmente distinta.

{% include note.html type="normal" text="Para o computador é irrelevante se a diferença entre duas datas é de um ano, um dia ou um milésimo de segundo. Sendo diferentes os números, as datas são também consideradas diferentes." %}

## Possíveis problemas

Já percebeu como isso pode gerar confusão e erro?

Se você estiver inserindo datas numa planilha sem atentar para o horário, poderá pensar que inseriu a mesma data em duas células diferentes, quando na verdade, para o computador, elas serão datas distintas.

De modo similar, o seu cálculo deixará de ser confiável se você estiver trabalhando numa planilha configurada para um determinado fuso horário e utilizar um complemento configurado para outro fuso horário.

{% include note.html type="normal" text="Lembre-se de que as planilhas do <b>Google Sheets</b> não estão “no Brasil”, mas “na nuvem”. Isso quer dizer que elas estão armazenadas em algum servidor do <b>Google</b> em qualquer parte do mundo, provavelmente em vários lugares ao mesmo tempo..." %}

Imagine que você esteja utilizando o complemento **Índices Previdenciários** e faça a consulta ao `SGS_TRD` no fuso horário de São Paulo, mas sua planilha esteja configurada para o fuso horário da Costa do Pacífico nos EUA.

Se a consulta foi feita às 23h do dia 01/03/2016, o complemento provavelmente terá utilizado o parâmetro `01/03/2016`, mas a planilha interpretará esse parâmetro como `02/03/2016` em razão da diferença de fuso horário. Se o índice for utilizado em algum cálculo, isso certamente produzirá erros, pois a TR Diária de 01/03/2016 será associada incorretamente ao dia 02/03/2016.

Além disso, ainda que você ajuste a sua planilha para o fuso horário adequado, ainda assim poderá ter problemas nos dias de início e fim do horário de verão...

## Como prevenir-se

Para evitar problemas desse tipo, os complementos e as planilhas de cálculo que você encontra na pasta "**Distribuição**" adotam um critério uniforme para a manipulação das datas: utilizam sempre o mesmo fuso horário, **_sem horário de verão_**. Como em *Google Sheets* essa opção só existe para o fuso horário de Greenwhich (GMT), esse é o fuso horário escolhido como padrão.

{% include note.html type="normal" text="Essa regra não é absoluta. Quando a data não é utilizada para cálculo, mas apenas para registrar o horário em que o usuário efetuou alguma operação, procura-se utilizar, sempre que possível, o fuso horário local e retornar a data em formato de texto simples. Um exemplo: as funções do complemento <b>Índices Previdenciários</b> retornam sempre na terceira coluna os dados da consulta efetuada, apenas para registro da fonte das informações, não para cálculo. Como nesse caso o que importa é saber o horário em que o usuário consultou o SGS ou o SIDRA, utiliza-se o fuso horário local, em formato de texto simples." %}

Portanto, se você está utilizando apenas as planilhas de cálculo da pasta "**Distribuição**", não há com que se preocupar, porque elas já vêm configuradas corretamente, sem que você precise fazer nada.

Pode ser, no entanto, que você queira utilizar algum complemento em outras planilhas suas ou de terceiros.

Nesse caso, para que os complementos se comportem na forma esperada, você deve ajustar manualmente as configurações de fuso horário da planilha, no menu `Arquivo > Configurações de planilha... > Fuso horário` e escolher `(GMT+00:00) GMT (sem horário de verão)`, conforme mostrado abaixo.

{% include image.html url="/images/Indices_Alteracao_Fuso.png" description="Tela da configuração do fuso horário" %}