---
date: 2017-01-21
title: Trabalhando com estatística
video_id: OHU7Wwu14v0
description: Como criar um serviço de estatística e registrar cálculos nesse serviço.
categories:
  - planilha-tc
  - planilha-rmi
  - planilha-atrasados
  - calculos-previdenciarios
resources:
  - name: "Link para a pasta Distribuição"
    link: https://drive.google.com/drive/folders/0B2B1B7RRK5HmS0I2clRTTTJiMXc
type: Video
set: primeiros-passos
set_order: 5
---

O complemento **Cálculos Previdenciários** permite que você configure uma única planilha para funcionar como serviço estatístico para registro unificado dos cálculos realizados por todos os integrantes do seu setor, da sua equipe ou do seu projeto.

É possível criar quantos serviços desse tipo você precisar.

Neste tutorial nós explicamos como configurar um novo serviço estatístico e como registrar novos cálculos nesse serviço.

## Criando um serviço

1. Acesse o link logo abaixo do vídeo para visualizar a pasta **Distribuição**. Você deve estar logado no *Google Drive*.
1. Abra a planilha `Estatística Template`.
1. Selecione `Arquivo > Fazer uma cópia...`
1. Escolha um nome para a planilha e defina a pasta de destino no seu drive. É possível criar novas pastas para melhor organização.
1. Clique em `OK` para gerar uma cópia da planilha no seu *Drive*.
1. Selecione `Ferramentas > Editor de scripts...` e, em seguida, `File > Manage versions...`. 
1. Clique em `Save new version` e em `OK`.
1. No menu `Publish > Deploy as web app...` escolha as opções `Execute as me` e `Anyone, even anonymous`. Esta parte é muito importante.
1. Em seguida, clique em `Deploy`. 
1. Aparecerá para você uma tela de autorização. Clique em `Review Permissions`.
1. Selecione sua conta do *Google Drive* e clique em `Permitir`.
1. Copie o *url* fornecido e distribua-o a sua equipe.

{% include note.html type="tip" text="Se esquecer o link, não se preocupe. É só abrir de novo o menu <code>Deploy as web app...</code> e o link estará lá para você copiá-lo de novo." %}

## Configurando a planilha para uso do serviço

1. Abra a planilha de cálculo.
1. Selecione `Complementos > Cálculos Previdenciários > Abrir`
1. Clique a aba da ferramenta de registro estatístico:
{% include image.html url="/images/Icone_Registro_Estatistico.png" description="Ícone Registro Estatístico" %}
1. Clique no botão `Novo`
1. Cole o *url* do serviço no campo `Insira o url do serviço`.
1. Clique no botão `Salvar`.

Se tudo deu certo, você agora verá os dados do serviço registrado.

{% include note.html type="normal" text="O url do serviço pode ser salvo como informação padrão do usuário. Se você fizer isso, poderá utilizar o mesmo url em todas as suas planilhas, sem precisa registrar o serviço toda vez que fizer um novo cálculo." %}

## Registrando um cálculo

1. Abra a planilha de cálculo. **Só registre o cálculo se já o tiver concluído**.
1. Selecione `Complementos > Cálculos Previdenciários > Abrir`.
1. Clique a aba da ferramenta de registro estatístico:
{% include image.html url="/images/Icone_Registro_Estatistico.png" description="Ícone Registro Estatístico" %}
1. Certifique-se de que existe um serviço de estatística já configurado e *online*.
1. Clique no botão `Enviar`.
1. Será aberta uma tela de confirmação dos dados do cálculo. Se tudo estiver correto, confirme o envio.

Os dados do cálculo deverão aparecer em poucos instantes na planilha do serviço estatístico.
