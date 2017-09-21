---
date: 2017-09-16
title: Instalando o complemento
categories:
  - indices-previdenciarios
description: Como instalar e utilizar o complemento Índices Previdenciários.
type: Document
---
O complemento **Índices Previdenciários** disponibiliza nas planilhas *Google Sheets* fórmulas customizadas para obtenção das séries históricas de índices de atualização e taxas de juros diretamente dos sistemas [SIDRA/IBGE](https://sidra.ibge.gov.br/home/abate/brasil){:target="_blank"} e [SGS/BACEN](https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries){:target="_blank"}.

Neste tutorial mostraremos como instalar e utilizar o complemento.

## Como instalar

Primeiro, acesse a página do complemento na *Chrome Web Store* por meio deste [link](https://chrome.google.com/webstore/detail/%C3%ADndices-previdenci%C3%A1rios/gjllgdjhcjmkpkpihigkighfegolinek?hl=pt-BR){:target="_blank"}.

Na porção superior direita da tela você verá um botão azul de instalação:

![Botão instalar]({{ site.baseurl }}{% link /images/Botao_instalar.png %})

Clique em "+". O *Google* abrirá automaticamente uma nova planilha, sem nome, para finalizar a instalação. Pode ser também que o *Google* lhe dê instruções adicionais. Basta segui-las.

## Autorizar e ativar

Uma vez instalado o complemento, um novo item aparecerá no menu "**Complementos**" de sua planilha, conforme a figura abaixo.

{% include image.html url="/images/Indices_Menu_Complemento.png" description="Menu Complementos." %}

Selecione a opção "**Usar nesta planilha**" para ativar as funções customizadas.

Na primeira vez em que você utilizar o complemento, o *Google* lhe mostrará uma tela de autorização. Siga as instruções.

{% include note.html type="normal" text="A tela de autorização poderá reaparecer para você no futuro se forem publicadas novas versões do complemento." %}

Uma vez autorizado e ativado o complemento, as funções customizadas estarão disponíveis normalmente em sua planilha. Elas aparecerão, inclusive, no *autocomplete*.

{% include image.html url="/images/Indices_Autocomplete.png" description="Autocomplete." %}

{% include note.html type="tip" text="Se você não estiver encontrando as funções no <b>autocomplete</b>, pode ser que não as tenha ainda habilitado na planilha. Nesse caso, selecione novamente a opção <b>Usar nesta planilha</b> no menu <b>Complementos</b> e elas deverão aparecer para você." %}

## Como usar as fórmulas

As funções de consulta são precedidas dos prefixos `SIDRA_` e `SGS_`.

Todas admitem dois argumentos opcionais: `dataInicial` e `dataFinal`.

Você pode informar essas datas por meio das funções nativas do *Google Sheets*, como a função `DATE()`, por exemplo, ou por meio de uma string no formato `dd/mm/aaaa`.

Sempre que você omitir argumentos, será utilizada a data de hoje.

{% include note.html type="tip" text="Como em todas as funções nativas ou customizadas, você também pode inserir, no lugar dos argumentos, uma referência a outra célula que contenha o valor da data a ser utilizado." %}

{% include note.html type="warning" text="Em <b>Google Sheets</b>, as strings devem ser sempre informadas entre aspas." %}

{% include note.html type="normal" text="Veja <a target='_blank' href='https://support.google.com/docs/answer/3092969'>aqui</a> detalhes sobre como utilizar a função <code>DATE()</code>." %}

Exemplos de consulta:

a) `SGS_SELIC_MENSAL(DATE(2016;1;1))`: retorna o histórico da Selic Mensal a partir de 01/01/2016 até hoje, já que a data final foi omitida;

b) `SGS_SELIC_MENSAL("01/01/2016")`: equivalente ao item "a" (repare nas aspas que definem a string);

c) `SGS_SELIC_MENSAL("01/01/2016"; "01/04/2016")`: retorna o histórico da Selic Mensal entre 01/01/2016 e 01/04/2016;

d) `SGS_SELIC_MENSAL(DATE(2016;1;1); DATE(2016;4;1))`: igual ao item "c".

O resultado da consulta é apresentado em três colunas, cada qual com a seguinte informação: 1) data do índice, 2) valor do índice e 3) texto com os dados da fonte. Veja abaixo:

{% include image.html url="/images/Indices_Dados_Baixados.png" description="Dados baixados." %}

Se a consulta não retornar valores, você verá na célula o erro `#REF`.
