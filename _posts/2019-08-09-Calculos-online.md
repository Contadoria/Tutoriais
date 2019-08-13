---
date: 2019-08-09
title: Cálculos Online
categories:
  - planilha-atrasados
description: Instruções detalhadas sobre como utilizar os formulários de cálculo online.
type: Document
---
Neste tutorial mostraremos como utilizar os formulários de cálculo online.


## Como acessar o formulário de cálculo online

Uma planilha de cálculo foi criada e configurada com objetivo de facilitar a liquidação dos julgados e está disponível na ferramenta de [Acesso Rápido](http://bit.ly/contadoria){:target="_blank"}.

{% include note.html type="normal" text="Você deve estar logado no <b>Google Drive</b>. Se ainda não estiver, clique em “<b>fazer login</b>” e digite seu nome de usuário e senha." %}

+ Caso seja o primeiro acesso, clique em `REVIEW PERMISSIONS`

{% include image.html url="/images/acesso rapido instala 1.png" description="Instalação 1" %}

+ Clique na sua conta *Google*.

+ Clique em `PERMITIR`

{% include image.html url="/images/acesso rapido instala 2.png" description="Instalação 2" %}

+ Quando a instalação for concluída, você visualizará a tela abaixo: 

{% include image.html url="/images/bitly.png" description="Tela Acesso Rápido" %}

+ Acesse a planilha clicando em `Liquidação`.

{% include image.html url="/images/Tela_Calculos_Online.png" description="Cálculos Online" %}



## Importando dados básicos do processo

É possível importar os dados básicos do processo, como, por exemplo, número do processo, nome da parte, data do protocolo e data da citação.

+ Acesse o [site do Juizado Especial Federal Cìvel de São Paulo](http://jef.trf3.jus.br/){:target="_blank"};
+ Digite o número do processo e clique em `Consultar`;
{% include image.html url="/images/Tela_Sisjef.png" description="SISJEF" %}
+ Selecione todas as informações pressionando `Control + A`;
+ Copie as informações pressionando `Control + C`;
+ Clique no botão de `Preenchimento automático` ao lado do Título `1. Dados do Processo`;
+ Cole as informações pressionando `Control + V` e clique no botão: {% include image.html url="/images/Botao_Confirmar.png" description="Botao_Confirmar" %}
+ Os dados serão transferidos para o formulário de cálculo online.

## Elaboração do cálculo

O formulário de cálculo exige a inserção dos seguintes dados **obrigatórios** (marcados com um **asterisco**):
+ Número do processo
+ Data do protocolo
+ Data da citação
+ Nome do Autor
+ Data final das diferenças
+ Espécie do benefício
+ Data de início do benefício (`DIB`)
+ Renda mensal inicial (`RMI`)


**Quadro espécies de benefício**

{% include image.html url="/images/Lista_Beneficios.png" description="Lista Benefícios" %}

Ao terminar de inserir os dados necessários para elaboração do cálculo, clique no botão: {% include image.html url="/images/Bota_Calcular_Ok.png" description="Botão Calcular Ok" %} 

Após o processamento do cálculo, será possível gerar:
+ um arquivo no formato `PDF` {% include image.html url="/images/Botao_Pdf.png" description="Botão PDF" %}
ou
+ uma imagem no formato `PNG` {% include image.html url="/images/Botao_Png.png" description="Botão PNG" %}

**PRONTO!**

O cálculo foi concluído e já foi gravado no seu computador.

{% include note.html type="normal" text="Normalmente os arquivos são gravados na pasta de <b>Downloads</b> do seu computador" %}

## Desconto de valores (evolução com base na aplicação de índices de reajuste legais)

Neste método, é necessário digitar os dados do benefício originário: 
+ Data de início do benefício (`DIB`)
+ Renda mensal Inicial (`RMI`)
+ Data de cessação do benefício (`DCB`), se for o caso
+ Índice teto (se houver)
+ Opção de calcular abono

{% include note.html type="normal" text="É possível descontar até 3 benefícios dessa forma." %}

## Desconto de valores (inserção em cada competência)

Neste método, o desconto deve ser efetuado em cada competência nas seções `8. Ajuste de Descontos (Renda)` e `9. Ajuste de Descontos (Abono)`.
+ Digite o mês ou ano que deseja realizar o desconto
+ Clique com o botão direito na competência e depois em `Editar`
+ Digite o valor a ser descontado e depois em `Confirmar`

{% include note.html type="normal" text="Utilize este método para descontar valores inferiores ao salário-mínimo ou superiores ao teto máximo de pagamento." %}
