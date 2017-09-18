---
date: 2017-09-16
title: Evitando problemas com datas
categories:
  - indices-previdenciarios
  - calculos-previdenciarios
  - desenvolvimento-de-planilhas
description: Este tutorial explica por que você pode ter problemas com as datas em Google Sheets e o que fazer. para prevenir-se
type: Document
---
Neste tutorial explicamos como o *Google Sheets* interpreta as datas inseridas nas planilhas e nos complementos,como e por que os cálculos com datas podem dar errado e o que se pode fazer para evitar que tais erros aconteçam.

## Como as datas são interpretadas em *Google Sheets*

Assim como em *Excel*, é também um desafio para o iniciante em *Google Sheets* descobrir como efetuar corretamente os cálculos com datas.

A razão da dificuldade está no modo peculiar como as datas são interpretadas pelas planilhas e pelos complementos. 

Para que as datas possam ser comparadas e utilizadas em cálculos matemáticos, os computadores as tratam como números sequenciais. Esse é o modo como distinguem dois instantes diferentes no tempo, cada instante correspondendo a um número único e irrepetível.

Já o ser humano expressa uma data utilizando três valores diferentes: um expresso com numeração sequencial e irrepetível (o ano) e outros dois expressos com numeração cíclica, que se repete de tempos em tempos (os meses e dias). Assim, na forma como o ser humano utiliza as datas em seu cotidiano, dois instantes diferentes no tempo podem trazer os mesmo valores para o mês e o dia.

Além disso, os computadores sempre levam em consideração o horário. Para uma planilha, o dia 01/04/2015 às 12h00 é sempre considerado como distinto do dia 01/04/2015 às 12h05, enquanto para um ser humano essa diferença pode ou não ser relevante, dependendo daquilo que se pretenda com o cálculo. 

Em matéria previdenciária, em geral, o horário é irrelevante e as duas "datas" do exemplo seriam provavelmente consideradas como idênticas para fins de cálculo de um benefício.

Por essas razões, os computadores costumam expressar as datas de dois modos:

1) como números sequenciais, quando são utilizadas num cálculo;

2) como um texto compreensível para o ser humano, quando são mostradas ao usuário.

Nas planilhas do *Google Sheets*, cada data corresponde a um número decimal cuja parte inteira significa o número de dias transcorridos desde 30/12/1899 e a parte fracionária ao horário do dia. Por exemplo: o número `42370,92` equivale às 22h00 do dia 01/01/2016. 

Assim, quando o usuário digita numa célula a data `01/01/2016`, para o computador a informação é lida como o número `42370`.

A situação se complica quando um complemento é integrado à planilha, porque no código executado nos complementos as datas e os horários são medidos de forma diferente.

Os complementos são escritos em Javascript. Nessa linguagem, os instantes são medidos em milissegundos transcorridos em relação ao início da "[Era Unix](https://pt.wikipedia.org/wiki/Era_Unix)".

Por exemplo, o instante `2016-01-02T00:00:00.000Z`, equivalente às 22h00 do dia 01/01/2016, horário de verão brasileiro, corresponde, em Javascript, ao número `1451692800000`. O número seguinte, `1451692800001`, embora represente uma diferença de apenas um milésimo de segundo em relação ao anterior, é tratado como uma data completamente distinta. Para o computador, não importa se a diferença é de um ano, um dia ou um milésimo de segundo. Sendo diferentes os números, as datas são também consideradas diferentes.

## Possíveis problemas

Percebeu como isso pode gerar confusão e erro?

Se você estiver inserindo datas numa planilha sem atentar para o horário, poderá pensar que inseriu a mesma data em duas células diferentes, quando na verdade, para o computador, elas serão datas distintas.

Um problema similar pode ocorrer se você estiver trabalhando numa planilha configurada para um determinado fuso horário e utilizar um complemento configurado para outro fuso horário.

> **Nota**: Lembre-se de que as planilhas do *Google Sheets* não estão "no Brasil", mas na "nuvem", isto é, em algum servidor do *Google*, provavelmente na California, mas possivelmente em qualquer lugar do mundo, até mesmo em vários lugares ao mesmo tempo...

Imagine que você esteja utilizando o complemento **Índices Previdenciários** e faça a consulta ao `SGS_TRD` no fuso horário de São Paulo, mas sua planilha esteja configurada para o fuso horário da Costa do Pacífico nos EUA.

Se a consulta foi feita às 23h do dia 01/03/2016, o complemento provavelmente terá utilizado o parâmetro `01/03/2016`, mas a planilha interpretará esse parâmetro como `02/03/2016` em razão da diferença de fuso horário. Se o índice for utilizado em algum cálculo, isso certamente produzirá erros, pois a TR Diária de 01/03/2016 será associada incorretamente ao dia 02/03/2016.

Além disso, ainda que você ajuste a sua planilha para o fuso horário adequado, ainda assim poderá ter problemas nos dias de início e fim do horário de verão...

## Como prevenir-se

Para evitar problemas desse tipo, os complementos e as planilhas de cálculo que você encontra na pasta "**Distribuição**" adotam um critério uniforme para a manipulação das datas: utilizam sempre o mesmo fuso horário, **_sem horário de verão_**. Como em *Google Sheets* essa opção só existe para o fuso horário de Greenwhich (GMT).

> **Nota**: Essa regra não é absoluta. Quando a data não é utilizada para cálculo, mas apenas para registrar o horário em que o usuário efetuou alguma operação, procura-se utilizar, sempre que possível, o fuso horário local e retornar a data em formato de texto simples. Um exemplo: as funções do complemento **Índices Previdenciários** retornam sempre na terceira coluna os dados da consulta efetuada, apenas para registro da fonte das informações, não para cálculo. Como nesse caso o que importa é saber o horário em que o usuário consultou o SGS ou o SIDRA, utiliza-se o fuso horário local, em formato de texto simples.

Portanto, se você está utilizando apenas as planilhas de cálculo da pasta "**Distribuição**", não há com que se preocupar, porque elas já vêm configuradas corretamente, sem que você precise fazer nada.

Pode ser, no entanto, que você queira utilizar algum complemento em outras planilhas suas ou de terceiros.

Nesse caso, para que os complementos se comportem na forma esperada, você deve ajustar manualmente as configurações de fuso horário da planilha, no menu `Arquivo > Configurações de planilha... > Fuso horário` e escolher `(GMT+00:00) GMT (sem horário de verão)`, conforme mostrado abaixo.

![Screenshot]({{ site.baseurl }}{% link /images/Indices_Alteracao_Fuso.png %})