---
date: 2017-09-16
title: Distorções nas datas
categories:
  - Índices Previdenciários
  - Cálculos Previdenciários
  - Desenvolvimento de Planilhas
description: "Como evitar distorções nas datas"
type: Document
---
É sempre um desafio trabalhar com datas, seja em *Google Sheets*, seja em *Excel*.

Neste tutorial nós explicamos como distorções nas datas podem ocorrer com o uso dos complementos e o que você deve fazer para que isso não lhe traga problemas.

## O que é uma data

Nas planilhas e nos complementos as datas têm sempre "duas faces": 

1) quando fazem parte de um cálculo (quando as inserimos como argumentos de uma fórmula, por exemplo), elas são computadas como números;

2) quando são mostradas ao usuário, elas se comportam como uma string (um texto) que expressa esse número em termos mais compreensíveis para o ser humano, tal como `01/02/2014 12:00:31`.

Em *Google Sheets*, o número que representa uma data significa, em sua parte inteira, o número de dias transcorridos desde 30/12/1899 e, em sua parte fracionária, o horário do dia. Por exemplo, o número `42370,92` equivale à string `01/01/2016 22:00:00`.

A situação se complica quando um complemento é integrado à planilha, porque no código executado nos complementos as datas e os horários são medidos de forma diferente.

> **Nota**: Se você está curioso, os complementos são escritos em uma versão simplificada do Javascript, que é a linguagem da Web. Nela, as datas são medidas em termos de milissegundos transcorridos na [Era Unix](https://pt.wikipedia.org/wiki/Era_Unix).

Uma mesma data computada pelo complemento pode ser interpretada como datas distintas para dois usuários situados em fuso horários diferentes.

## Qual o problema?

Já percebeu como isso pode gerar distorções?

Imagine que você esteja utilizando o complemento **Índices Previdenciários** e faça a consulta ao `SGS_TRD` no fuso horário de São Paulo, mas sua planilha esteja configurada para o fuso horário da Costa do Pacífico nos EUA.

> **Nota**: Lembre-se de que as planilhas do *Google Sheets* não estão "no Brasil", mas na "nuvem", isto é, em algum servidor do *Google*, provavelmente na California, mas possivelmente em qualquer lugar do mundo, até mesmo em vários lugares ao memso tempo...

Se a consulta foi feita às 23h do dia 01/03/2016, o complemento provavelmente terá utilizado o parâmetro `01/03/2016`, mas a planilha interpretará esse parâmetro como `02/03/2016` em razão da diferença de fuso horário. Se o índice for utilizado em algum cálculo, isso certamente produzirá erros, pois a TR Diária de 01/03/2016 será associada incorretamente ao dia 02/03/2016.

Algo similar pode ocorrer nos dias de início e fim do horário de verão.

## A solução

Para evitar problemas desse tipo, os complementos e as planilhas de cálculo que você encontra na pasta "**Distribuição**" adotam um critério uniforme para a manipulação das datas: usam sempre, como padrão, o fuso horário de Greenwhich (GMT), porque esse é o único fuso com a opção **_sem horário de verão_** em *Google Sheets*. 

> **Nota**: Essa regra não é absoluta. Quando a data não é utilizada para cálculo, mas apenas para registrar o horário em que o usuário efetuou alguma operação, procura-se utilizar, sempre que possível, o fuso horário local e retornar a data em formato de texto simples. Um exemplo: as funções do complemento **Índices Previdenciários** retornam sempre na terceira coluna os dados da consulta efetuada, apenas para registro da fonte das informações, não para cálculo. Como nesse caso o que importa é saber o horário em que o usuário consultou o SGS ou o SIDRA, utiliza-se o fuso horário local, em formato de texto simples.

Portanto, se você está utilizando apenas as planilhas de cálculo da pasta "**Distribuição**", não há com que se preocupar, porque elas já vêm configuradas corretamente, sem que você precise fazer nada.

Pode ser, no entanto, que você queira utilizar algum complemento em outras planilhas suas ou de terceiros.

Nesse caso, para que os complementos se comportem na forma esperada, você deve ajustar manualmente as configurações de fuso horário da planilha, no menu `Arquivo > Configurações de planilha... > Fuso horário` e escolher `(GMT+00:00) GMT (sem horário de verão)`, conforme mostrado abaixo.

![Screenshot](/images/Indices_Alteracao_Fuso.png)