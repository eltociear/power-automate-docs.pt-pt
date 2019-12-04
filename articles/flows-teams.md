---
title: Aprender a criar e a gerir fluxos no Microsoft Teams | Microsoft Docs
description: Crie e faça a gestão dos fluxos para publicar mensagens a pedido, @mention utilizadores e canais, publicar cartões com opções de resposta e muito mais.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: a2a9b5d5a6ed8305ed3e7c29717ef19978bae0a7
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74367070"
---
# <a name="power-automate-in-teams"></a>Power Automate no Teams
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

### <a name="prerequisites"></a>Pré-requisitos

1. Acesso ao Microsoft Teams.
1. Acesso ao Power Automate.

## <a name="install-the-power-automate-app-in-teams"></a>Instalar a aplicação do Power Automate no Teams

Siga estes passos para instalar a aplicação do Power Automate no Microsoft Teams.

1. Inicie sessão no Microsoft Teams.

1. Toque no ícone **Aplicações** na parte inferior esquerda da barra de navegação do Teams.

    ![Selecionar aplicações](media/flows-teams/apps.png)

1. Selecione a aplicação **Flow**. Poderá ter de pesquisar **Flow** se a aplicação não for apresentada.

    ![Selecionar a aplicação Flow](media/flows-teams/select-flow-app.png)

1. Selecione **Instalar**.

    ![Botão Instalar](media/flows-teams/select-install.png)

1. O Power Automate está, agora, instalado.

    ![Instalado](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Criar um fluxo no Teams

1. Inicie sessão no Microsoft Teams.

1. Selecione a ligação **Mais aplicações adicionadas** (...) na barra de navegação e, em seguida, selecione a aplicação **Flow**.

    ![Ícone de aplicações adicionadas](media/flows-teams/added-apps-icon.png)

1. Se ainda não o tiver feito, poderá ter de iniciar sessão e conceder permissões.

    ![Iniciar sessão](media/flows-teams/grant-permissions-sign-in.png)


    Repare nos seguintes separadores:

    ![Página de destino do Flow](media/flows-teams/flow-landing-page.png)

    Nome|Finalidade
    ----|-----|
    Conversação|Interagir com o bot do Flow.
    Fluxos|Criar e gerir fluxos.
    Aprovações|Apresenta uma lista de pedidos de aprovação recebidos e enviados.
    Sobre|Apresenta a versão e outras informações do Power Automate.


    Agora, pode ver todos os fluxos que criou com o estruturador do Power Automate (se existirem). 

    Também pode criar fluxos a partir de um modelo personalizado ou de um modelo em branco, tal como faz com o estruturador do Power Automate. 

## <a name="manage-approvals"></a>Faça a gestão de aprovações

Pode gerir [aprovações](modern-approvals.md) no Microsoft Teams, tal como faz no Power Automate. Siga estes passos para gerir as aprovações:

1. Inicie sessão no Microsoft Teams.
1. Selecione o separador **Aprovações**.

    ![Separador Aprovações](media/flows-teams/approvals-tab.png)

    Verá os seguintes subseparadores:

    Separador|Finalidade
    ----|-----|
    Recebidos|Apresenta uma lista de pedidos de aprovação que recebeu e que aguardam a sua ação.
    Enviados|Apresenta uma lista de pedidos de aprovação que enviou e que aguardam a ação de outros utilizadores.
    Histórico|Apresenta uma lista de pedidos de aprovação recebidos e enviados.
    Criar um fluxo de aprovação|Criar fluxos de aprovação.

1. Selecione os separadores **Recebidos**, **Enviados** ou **Histórico** para saber mais.

    ![Separador Aprovações](media/flows-teams/approvals-tab-2.png)

1. Selecione **Criar fluxo de aprovação** para criar um fluxo de aprovação.

    ![Separador Aprovações](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>Utilizar o bot com fluxos

### <a name="list-and-launch-flows-with-the-bot"></a>Listar e iniciar fluxos com o bot

> [!TIP]
> O bot lista e executa fluxos que são acionados por um agendamento ou acionados manualmente, sem intervenção do utilizador.

1. Inicie sessão no Microsoft Teams.
1. Selecione a ligação **Mais aplicações adicionadas** (...) na barra de navegação e, em seguida, selecione a aplicação **Flow**.

    ![Ícone de aplicações adicionadas](media/flows-teams/added-apps-icon.png)
    
1. Selecione o separador **Conversação**.

    ![Separador Conversação](media/flows-teams/conversations-tab.png)

No separador **Conversação**, pode enviar comandos para o bot, que responde com a realização das ações que ordenar. Por exemplo, para listar os fluxos e executar o fluxo com índice 1, execute os seguintes comandos:

- ```List flows``` – o bot apresenta uma lista dos fluxos, antecedidos por um número de índice.
- ```Run flow 1``` – executa o fluxo número 1. Aqui, *1* é o número de índice do fluxo que pretende executar.

   ![Comandos do bot](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>Obter a descrição dos fluxos

Para obter a descrição do fluxo com o índice 1 na lista de fluxos, execute ```describe flow 1```. A resposta do bot será semelhante a esta imagem:

   ![Descrever fluxos](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>Obter a lista de comandos do bot

Para obter a lista de comandos processados pelo bot, execute este comando: ```learn more``` 

A resposta do bot será semelhante a esta imagem:

![Descrever fluxos](media/flows-teams/bot-learn-more.png) 
