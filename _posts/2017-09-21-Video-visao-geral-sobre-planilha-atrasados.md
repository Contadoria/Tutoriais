---
date: 2017-01-21
title: Atrasados - Visão Geral
video_id: DZ1vVOwCSnE
description: Visão geral sobre a planilha CalculoAtrasados.
categories:
  - planilha-atrasados
type: Video
set: utilizando-as-planilhas
set_order: 4
---

A planilha `CalculoAtrasados` apura os valores da causa e da condenação, os dados para expedição de RPV e os honorários advocatícios a partir dos parâmetros do benefício e do processo e dos critérios de atualização fornecidos pelo usuário.

Neste tutorial vamos dar instruções básicas sobre o uso da planilha.

## Transferindo informações de uma planilha de cálculo de RMI

É possível transferir as informações de uma RMI apurada anteriormente.

Para tanto, siga as instruções:

1. Abra a planilha de cálculo da RMI e selecione `Complementos > Cálculos Previdenciários > Abrir`.
1. Clique no ícone da ferramenta da área de transferência (![Ícone Área Transferencia]({{ site.baseurl }}{% link /images/Icone_Area_Transferencia.png %})).
1. Clique no botão `Copiar` (![Botão Copiar Área Transferência]({{ site.baseurl }}{% link /images/Botao_Copiar_Area_Transferencia.png %})).
1. Retorne para a planilha de cálculo de atrasados e clique no botão `Colar` (![Botão Colar Área Transferência]({{ site.baseurl }}{% link /images/Botao_Colar_Area_Transferencia.png %})).

Se tudo deu certo, os dados foram transferidos para os campos específicos.

## Usando a planilha

Roteiro simplificado para calcular atrasados:

1. Na aba `Processo`, defina a natureza da ação, se *concessória* ou *revisional*. Selecione o **critério de alçada**.
1. Na aba `Atualização`, insira o *índice de reposição do teto*, se houver. Defina a *data da atualização do cálculo*.
1. Na aba `Benefício Devido`, pode ser inserida a *data de cessação do benefício (DCB)*, bem como definidos limites para o cálculo nos campos *Início e Final das diferenças*, inserindo as datas no campo *Modificadores*.
1. Na aba `Benefício Pago`, a entrada de dados está vinculada à seleção da opção *revisional* na natureza do ação.
1. Eventuais descontos devem ser lançados na aba `Descontos` nas colunas específicas.
1. O resultado do cálculo encontra-se na aba verde `Demonstrativo`.
1. O cálculo de alçada encontra-se nas abas verdes `Alçada Analítico` e `Alçada Sintético`
1. Os valores discriminados para requisição de pagamento encontram-se na aba `Requisições`
