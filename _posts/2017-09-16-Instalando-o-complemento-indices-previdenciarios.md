---
date: 2017-09-16
title: Primeiros passos
categories:
  - Índices Previdenciários
description: "Como instalar e usar o complemento"
type: Document
---
O complemento **Índices Previdenciários** disponibiliza nas planilhas *Google Sheets* fórmulas customizadas que permitem a consulta direta aos sistemas [SIDRA/IBGE](https://sidra.ibge.gov.br/home/abate/brasil) e [SGS/BACEN](https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries) para obtenção das séries históricas de índices de atualização e taxas de juros utilizados nos cálculos previdenciários.

## Como instalar

Acesse a página do complemento na *Chrome Web Store* por meio deste [link](https://chrome.google.com/webstore/detail/%C3%ADndices-previdenci%C3%A1rios/gjllgdjhcjmkpkpihigkighfegolinek?hl=pt-BR).

Na porção superior direita da tela você verá um botão azul de instalação:

![Botão instalar]({{ site.baseurl }}{% link /images/Botao_instalar.png %})

Clique em "+". O *Google* abrirá automaticamente uma nova planilha, sem nome, para finalizar a instalação. Pode ser também que o *Google* lhe dê instruções adicionais. Basta segui-las.

## Autorizar e ativar

Uma vez instalado o complemento, um novo item aparecerá no menu "**Complementos**" de sua planilha, conforme a figura abaixo.

![Screenshot]({{ site.baseurl }}{% link /images/Indices_Menu_Complemento.png %})

Selecione a opção "**Usar nesta planilha**" para ativar as funções customizadas.

Na primeira vez que você utilizar o complemento, o *Google* lhe mostrará uma tela de autorização. Siga as instruções.

> **Nota**: A tela de autorização poderá reaparecer para você no futuro se forem publicadas novas versões do complemento.

Uma vez autorizado e ativado o complemento, as funções customizadas estarão disponíveis normalmente em sua planilha. Elas aparecerão, inclusive, no *autocomplete*.

![Screenshot]({{ site.baseurl }}{% link /images/Indices_Autocomplete.png %})

> **Dica**: Se você não estiver encontrando as funções no *autocomplete*, pode ser que não as tenha ainda habilitado na planilha que está usando. Nesse caso, selecione novamente a opção "**Usar nesta planilha**" no menu "**Complementos**" e elas deverão aparecer para você.

## Como usar as fórmulas

As funções de consulta são precedidas dos prefixos `SIDRA_` e `SGS_`.

Todas admitem dois argumentos opcionais: `dataInicial` e `dataFinal`.

Você pode informar essas datas por meio das funções nativas do *Google Sheets*, como a função `DATE()`, por exemplo, ou por meio de uma string no formato `dd/mm/aaaa`.

Sempre que você omitir argumentos, será utilizada a data de hoje.

> **Dicas**: 
> 1) Como em todas as funções nativas ou customizadas, você também pode inserir, no lugar dos argumentos, uma referência a outra célula que contenha o valor da data a ser utilizado. 
> 2) Em *Google Sheets*, as strings devem ser sempre informadas entre aspas.
> 3) Para detalhes sobre como utilizar a função `DATE()`, veja [aqui](https://support.google.com/docs/answer/3092969).

Exemplos de consulta:

a) `SGS_SELIC_MENSAL(DATE(2016;1;1))`: retorna o histórico da Selic Mensal a partir de 01/01/2016 até hoje, já que a data final foi omitida;

b) `SGS_SELIC_MENSAL("01/01/2016")`: equivalente ao item "a" (repare nas aspas que definem a string);

c) `SGS_SELIC_MENSAL("01/01/2016"; "01/04/2016")`: retorna o histórico da Selic Mensal entre 01/01/2016 e 01/04/2016;

d) `SGS_SELIC_MENSAL(DATE(2016;1;1); DATE(2016;4;1))`: igual ao item "c".

O resultado da consulta é apresentado em três colunas, cada qual com a seguinte informação: 1) data do índice, 2) valor do índice e 3) texto com os dados da fonte. Veja abaixo:

![Screenshot]({{ site.baseurl }}{% link /images/Indices_Dados_Baixados.png %})

Se a consulta não retornar valores, você verá na célula o erro `#REF`.