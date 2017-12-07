---
date: 2017-12-06
title: Como criar documentos, utilizando dados das planilhas para preenchimento de um modelo
categories:
  - planilha-tc
  - planilha-rmi
  - planilha-atrasados
description: Instruções detalhadas sobre como obter um documento, utilizando os dados das planilhas para preenchimento de um modelo.
type: Document
set: primeiros-passos
set_order: 7
---
Neste tutorial mostraremos como você pode gerar um documento, utilizando os dados das planilhas para preenchimento de um modelo.

## Como instalar o complemento Documentos da Contadoria

Primeiro, acesse a página do complemento na *Chrome Webstore* por meio deste [link](https://script.google.com/macros/s/AKfycbytTXJLRgTDk3g3Sd935CEZR89v1zp7EHHrdXgzgsb_IVqZ4ko/exec){:target="_blank"}.

Leia e aceite os **termos de uso**.

Clique em `INSTALAR`

Clique em `Avançado`

Clique em `Acessar Contadoria Drive (não seguro)`

Clique em `PERMITIR`

Quando a instalação for concluída, você visualizará a tela abaixo: 

{% include image.html url="/images/Tela_Instalacao_Documentos.png" description="Tela Instalação" %}


## Criando um modelo para servir de base para importação dos dados das planilhas

{% include note.html type="normal" text="Você deve estar logado no <b>Google Drive</b>. Se ainda não estiver, clique em “<b>fazer login</b>” e digite seu nome de usuário e senha." %}

Para criar um modelo de Documento, clique com o botão **direito** do mouse e acesse `Documentos Google`

{% include image.html url="/images/Tela_Criar_Documento.png" description="Tela Documentos" %}

Elabore um documento com as informações pertinentes

As informações podem ser importadas, utilizando *tags* como por exemplo:

+ {% raw %}{{DIB}}{% endraw %}: retorna o valor do intervalo "DIB", "DIBOriginario", "DER" ou "-";
+ {% raw %}{{DER}}{% endraw %}: retorna o valor do intervalos "DER" ou  "-"';
+ {% raw %}{{DCB}}{% endraw %}: retorna o valor do intervalo "DCB", "DCBOriginario" ou "-";
+ {% raw %}{{RMI}}{% endraw %}: retorna o valor do intervalo "RMI", "RMIInformada", "RMIOriginario" ou "-";
+ {% raw %}{{RMI_Extenso}}{% endraw %}: retorna o valor dos mesmos intervalo de {{RMI}}, mas por extenso, não em algarismos;
+ {% raw %}{{RMA}}{% endraw %}: retorna o valor do intervalo "RMA", "RMAOriginario" ou "-";
+ {% raw %}{{RMA_Extenso}}{% endraw %}: retorna o valor dos mesmos intervalo de {{RMA}}, mas por extenso, não em algarismos;
+ {% raw %}{{HOJE}}{% endraw %}: retorna a data atual em formato "dd/mm/aaaa";
+ {% raw %}{{HOJE_Extenso}}{% endraw %}: retorna a data atual, em formato “dd de mmmm de aaaa”;
+ {% raw %}{{TC}}{% endraw %}: retorna a lista de períodos listados em seguida ao intervalo “TCProcessado”, com as linhas numeradas em sequência, ou “-”;
+ {% raw %}{{Especie}}{% endraw %}: retorna a espécie do benefício, no formato “n - nome” ou “-”;
+ {% raw %}{{NB}}{% endraw %}: retorna o valor do intervalo “NB”, “NBOriginario” ou "-";
+ {% raw %}{{Processo}}{% endraw %}: retorna o valor do intervalo “Processo” ou "-";
+ {% raw %}{{Autor}}{% endraw %}: retorna o valor do intervalo “Autor” ou "-";
+ {% raw %}{{Reu}}{% endraw %}: retorna o valor do intervalo “Reu” ou "-";
+ {% raw %}{{Citacao}}{% endraw %}: retorna o valor do intervalo “Citacao” ou "-";
+ {% raw %}{{Protocolo}}{% endraw %}: retorna o valor do intervalo “Protocolo” ou "-";

Você pode também criar tags customizados, utilizando a sintaxe {% raw %}{{{% endraw %}intervalo{% raw}}}{% endraw %}, na qual “intervalo” corresponde a um nome de intervalo na planilha. Você também pode utilizar **disjuntores**, como, por exemplo, {% raw %}{{{% endraw %}intervalo1 || intervalo2{% raw %}}}{% endraw %}, caso em que, não havendo valores para o “intervalo1” será retornado o valor do “intervalo2”. Também é possível utilizar uma expressão literal entre aspas. Por exemplo, o tag {{intervalo1 || intervalo2 || “-”}} instrui o WebApp a substituir o tag por um traço caso não sejam encontrados valores para nenhum dos intervalos.

{% include image.html url="/images/Tela_Criar_Documento_02.png" description="Tela Documentos" %}

## Criando um documento a partir de dados das planilhas

{% include note.html type="normal" text="Você deve estar logado no <b>Google Drive</b>. Se ainda não estiver, clique em “<b>fazer login</b>” e digite seu nome de usuário e senha." %}

Selecione as planilhas que deseja extrair os dados e clique com o botão **direito** do mouse e acesse `Abrir com > Contadoria Documentos`

{% include image.html url="/images/Tela_Complemento_Documentos.png" description="Tela Documentos" %}

Clique no botão para selecionar um modelo de documento

{% include image.html url="/images/Tela_Complemento_Documentos_02.png" description="Tela Documentos" %}

Selecione um modelo e clique em `Selecionar`

{% include image.html url="/images/Tela_Complemento_Documentos_03.png" description="Tela Documentos" %}

Digite um identificador e clique em `Criar`.

{% include image.html url="/images/Tela_Complemento_Documentos_04.png" description="Tela Complemento 02" %}

**PRONTO!**

O documento foi criado e armazenado no *Drive*. Agora você pode abri-lo e visualizá-lo.
