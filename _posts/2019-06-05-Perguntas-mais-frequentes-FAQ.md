---
date: 2019-06-05
title: Perguntas mais frequentes (FAQ)
categories:
  - indices-previdenciarios
  - calculos-previdenciarios
  - desenvolvimento-de-planilhas
  - planilha-tc
  - planilha-rmi
  - planilha-atrasados
description: Compilação das perguntas mais frequentes dos usuários.
type: Document
---



## Geral

**Qual a melhor forma de localizar os links de instalação das ferramentas?**
+ Acesse [link](https://bit.ly/contadoria){:target="_blank"}

**Pra que serve o endereço https//bit.ly/contadoria?**
+ Nesse endereço, centralizamos os links de acesso atualizados para as ferramentas, bem como para planilha online.

**Não consigo acessar o complemento `Contadoria Planilhas`. O que devo fazer?**
+ Reinstale o complemento (acesse [https//bit.ly/contadoria](https://bit.ly/contadoria){:target="_blank"})

**Qual a diferença entre criar uma planilha pelo complemento `Contadoria Planilhas` e criar uma cópia de uma planilha salva no Meu Drive?**
+ Utilizando o complemento `Contadoria Planilhas`, o usuário garante que está obtendo sempre a versão mais atualizada distribuída.

**Como consigo extrair informações do CNIS**
+ Instale o complemento `Cálculos Previdenciários` (acesse [https//bit.ly/contadoria](https://bit.ly/contadoria){:target="_blank"})
+ Tutorial completo neste [link](https://contadoria.github.io/Tutoriais/planilha-tc/planilha-rmi/planilha-atrasados/Video-extraindo-dados-cnis/)

## CalculoTC

**Pra que serve a aba `TCAdicionado?`**
+ Para adicionar um tempo líquido em formato anos, meses e dias.


**Quais as formas de alterar a apuração da carência de um período?**
+ é possível não computar a carência com o lançamento na coluna N da aba `TCDiscriminado`;
+ é possível alterar a carência apurada automaticamente na coluna V da aba `ModificadoresCarencia`. **Atente que os períodos desta aba são recalculados caso sejam alterados os períodos na aba `TCDiscriminado`.**


**Como apurar o tempo de contribuição com as devidas conversões de uma aposentadoria da pessoa portadora de deficiência?**
+ Defina essa opção na célula K9 da aba `Processo`: `Sim`
+ Classifique os períodos lançados na coluna H da aba `TCDiscriminado`. Se não for lançada nenhuma classificação, o período será definido como `1 - Comum`, portanto sem deficiência.

## CalculoRMI

**Qual a melhor forma de preencher o valor de um salário-mínimo em determinada competência?**
+ Preencher `Sim` nas células correspondentes da coluna H da aba `Modificadores2`.


**É possível calcular o benefício com base na média dos 36 últimos salários de contribuição?**
+ Sim. Em caso de direito adquirido, preencha a data no campo F14 e selecione a sistemática no campo F17 da aba `Modificadores1`.


## CalculoAtrasados
**Qual a diferença entre os campos `DCB` (célula D9 da aba `BeneficioDevido`) e `DataFinaldasDiferencas` (célula J9 da aba `BeneficioDevido`)?**
+ Quando utilizamos a `DCB`, o cálculo será realizado até esta data **com** apuração do décimo terceiro proporcional.
+ Quando utilizamos a `DataFinalDiferencas`, o cálculo será realizado até esta data **sem** apuração do décimo terceiro proporcional.



**É possível elaborar cálculo sem juros de mora?**
+ Sim. Basta deletar o conteúdo do campo referente aos juros de mora (célula D11 da aba `Atualizacao`).



**É possível apurar o valor das doze parcelas vincendas com base na diferença entre o valor devido e o valor pago?**
+ Sim. Altere o campo `NaturezaAcao` (célula D11 da aba `Processo`) para `"2 - Revisional"`.



**Tentei converter um auxílio-doença em aposentadoria por invalidez, mas o valor da renda não foi alterado. Como configurar a planilha?**
+ Para realizar esse cálculo, devem ser preenchidos os campos: 
+ Alterar a base para reajuste (célula D5 da aba `Atualizacao`): `3 - RMI no originário e SB no derivado`
+ Preencher `DCB`do benefício originário (célula D9 da aba `Atualizacao`);
+ Preencher `Especie` do benefício derivado (célula D18 da aba `Atualizacao`);
+ Preencher o valor do salário-de-benefício do benefício originário (célula J10 da aba `Atualização`). 


**Para fazer um cálculo referente ao desdobramento de pensão, qual a forma de preenchimento das Quotas (aba `Desdobro`)?**
+ Preencha a fração com o sinal de "=" antes. Por exemplo: =1/2


**Onde preencho o índice de reposição do teto?**
+ Célula D6 da aba `Atualizacao`.
