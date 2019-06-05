---
date: 2019-06-05
title: Perguntas mais frequentes
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


## Perguntas mais frequentes (FAQ)



**Qual a melhor forma de localizar os links de instalação das ferramentas?**
+ Acesse [https//bit.ly/contadoria](https://bit.ly/contadoria){:target="_blank"}



**Não consigo acessar o complemento "Contadoria Planilhas". O que devo fazer?**
+ Resinstale o complemento (acesse o [https//bit.ly/contadoria](https://bit.ly/contadoria){:target="_blank"})



**Qual a diferença entre os campos `DCB` (célula D9 da aba BeneficioDevido) e `DataFinaldasDiferencas` (célula J9 da aba BeneficioDevido)?
+ Quando utilizamos a `DCB`, o cálculo será realizado até esta data **com** apuração do décimo terceiro proporcional.
+ Quando utilizamos a `DataFinalDiferencas`, o cálculo será realizado até esta data **sem** apuração do décimo terceiro proporcional.



**É possível elaborar cálculo sem juros de mora?
+ Sim. Basta deletar o conteúdo do campo referente aos juros de mora (célula D11).



**É possível apurar o valor das doze parcelas vincendas com base na diferença entre o valor devido e o valor pago?**
+ Sim. Altere o campo `NaturezaAcao` (célula D11 da aba Processo) para **"2 - Revisional"**.



**Tentei converter um auxílio-doença em aposentadoria por invalidez, mas o valor da renda não foi alterado.**
+ Para realizar esse cálculo, devem ser preenchidos os campos: 

{% include screenshot.html url="/images/Issues_Popup.png" description="Popup" %}
