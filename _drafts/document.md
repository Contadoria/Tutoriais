---
date:
title:
# Cada nova categoria deve ser também criada pela inclusão de um novo arquivo na pasta
# '_category'. Insira aqui o "tag", que deve ser criado sempre sem espaços e sem acentos.
# Obedeça o formato <espaço><espaço>- ....
categories:
  - indices-previdenciarios
  - desenvolvimento-de-planilha
description: 
type: Document
---
Sempre comece o texto com uma breve introdução, de um a três parágrafos.

## Cada título, para ser mostrado também no índice lateral, deve ser de nível 2. Daí a utilização de "##"

Para cofigurar um link a ser aberto em uma nova janela do browser, você pode inserir o html diretamente no markdown ou utilizar:

[texto](url){:target="_blank"}.

Para incluir screenshots, temos uma template pré-formatado. Utilize:
{% include image.html url="/images/[nome do arquivo].png" description="[insira aqui uma descrição breve]" %}

Para inserir notas, você pode usar o markdown comum, iniciando com ">". Todavia, para sofisticar um pouco a formatação e melhorar a comunicação visual, estão disponíveis quatro formatos diferentes de notas: 'tip' (dica), 'warning' (atenção), 'danger' (perigo) e 'normal'. 

Nesse caso, qualquer formatação no texto deve ser inserida como HTML e covê não pode usar as aspas duplas retas - "" - deve utilizar ou as aspas curvas - “” - ou as aspas simples - ''.

Siga os modelos abaixo:

{% include note.html type="normal" text="[insira aqui o texto, formatando-o em HTML]" %}
{% include note.html type="tip" text="[insira aqui o texto, formatando-o em HTML]" %}
{% include note.html type="warning" text="[insira aqui o texto, formatando-o em HTML]" %}
{% include note.html type="danger" text="[insira aqui o texto, formatando-o em HTML]" %}

Para fazer referência a código Javascript, fórmulas, variáveis ou constantes, utilize `código`.