---
title: Iniciar fluxos com bttns | Microsoft Docs
description: Saiba como iniciar os fluxos com um bttn
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
ms.date: 05/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4eaafb1a551cc3333cde2058aebc41076b0267bd
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297148"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Executar fluxos com botões físicos (bttns) da The Button Corporation (Pré-visualização)

Acione os fluxos ao premir um bttn (um botão físico da [The Button Corporation](https://my.bt.tn/)). Por exemplo, pode premir um bttn que acione um fluxo para executar estas tarefas:

* entra em contacto com o suporte técnico, com informações de localização
* envia um e-mail para a equipa
* bloqueia o calendário
* reorganiza os fornecimentos

> [!IMPORTANT]
> Tem de [registar](https://my.bt.tn/) o bttn antes de poder utilizá-lo num fluxo.
> 
> [!TIP]
> Configure todas as propriedades de bttn, como o nome, a localização e o endereço de e-mail no [site bttn](https://my.bt.tn/) antes de criar o fluxo.
> 
> 

Também pode acionar um fluxo com um [botão físico Flic](flic-button-flows.md).

## <a name="prerequisites"></a>Pré-requisitos
* Acesso ao [Power Automate](https://flow.microsoft.com).
* Pelo menos um [bttn registado](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>Criar um fluxo acionado por um bttn
Nestas instruções, utilizamos um modelo de suporte técnico para criar um fluxo que pode acionar com um único toque de um [bttn](https://my.bt.tn/). Ao ser executado, o fluxo gera um pedido de suporte e envia-o para o suporte técnico. O pedido de suporte fornece ao suporte técnico a localização da sala onde é necessária assistência. Estas instruções demonstram como criar este fluxo a partir de um modelo, mas pode utilizar o modelo em branco, que lhe dá controlo total sobre todos os aspetos do fluxo.

Pode utilizar qualquer um destes modelos para criar rapidamente fluxos para o seu bttn e ligar ao Zendesk, Google e SharePoint, entre outros:

![modelos bttn](./media/bttn-button-flows/bttn-templates.png)

Sugestão: para o efeito destas instruções, dê um nome ao bttn que represente uma sala de conferências num edifício de escritórios.

As definições do bttn devem assemelhar-se a este exemplo (do site bttn):

![modelos bttn](./media/bttn-button-flows/bttn-config.png)

Agora que registou e configurou o bttn, vamos começar a criar o fluxo.

### <a name="sign-in-and-select-a-template"></a>Iniciar sessão e selecionar um modelo
1. Iniciar sessão no [Power Automate](https://flow.microsoft.com).
   
    ![iniciar sessão](./media/bttn-button-flows/sign-into-flow.png)
   
    Nota: em alternativa, pode criar fluxos na aplicação móvel Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows).
2. Introduza **bttn** na caixa de pesquisa e, em seguida, selecione o ícone de pesquisa.
   
    ![procurar](./media/bttn-button-flows/bttn-search-template.png)
   
    Depois de selecionar o ícone de pesquisa, são apresentados todos os modelos que pode utilizar com bttns.
3. Selecione o modelo **Utilizar Bttn para convocar o suporte técnico para a sala de reuniões**.
   
    ![modelo de suporte](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-power-automate-to-connect-to-your-bttn"></a>Autorizar a ligação do Power Automate ao bttn
1. Se lhe for pedido, inicie sessão no bttn e nos serviços do Office 365 Outlook, o que irá ativar o botão **Continuar**.
   
    ![credenciais](./media/bttn-button-flows/bttn-provide-credentials.png)
2. Ao iniciar sessão no serviço bttn, autorize o Power Automate a utilizar os bttns.
   
    **Importante**: se não autorizar o Power Automate a utilizar os bttns, não poderá vê-los nem ligar-se aos mesmos a partir do Power Automate.
   
    ![autorizar](./media/bttn-button-flows/authorize-bttn.png)
3. Depois de iniciar sessão nos dois serviços, selecione **Continuar**.
   
    ![Continuar](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Selecionar o bttn que aciona o fluxo
1. No cartão **Quando um bttn é premido**, abra a lista de IDs de bttns e, em seguida, selecione o bttn que quer utilizar.
   
    ![selecionar bttn](./media/bttn-button-flows/bttn-id.png)
   
    O fluxo deve, agora, assemelhar-se a este exemplo.
   
    ![descrição geral do fluxo](./media/bttn-button-flows/bttn-done.png)
2. Dê um nome ao fluxo e, em seguida, selecione **Criar fluxo** para guardá-lo.
   
    ![guardar fluxo](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Testar o fluxo e confirmar os resultados
1. Prima o botão no bttn.
2. Veja o histórico da execução do fluxo para se certificar de que foi executado com êxito.
   
    Pode verificar o histórico de execuções no site do Power Automate ou no dispositivo móvel.
   
    Nota: o estado da execução está definido como **em execução** até alguém selecionar **Reconhecer** no e-mail de pedido de suporte.
3. Também pode confirmar que o e-mail foi enviado para a equipa de suporte.
   
    Se seguiu as instruções até agora, o e-mail de suporte assemelha-se a este exemplo:
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Resolução de Problemas
* Se o fluxo não tiver sido acionado, inicie sessão no site da The Button Corporation e verifique se a atividade dos botões (toques) está a ser registada.
* Também pode aprofundar o nível de detalhe da atividade de execução no site do Power Automate e verificar se existem mensagens de erro.

## <a name="more-information"></a>Mais Informações
* [Partilhe fluxos de botões](share-buttons.md).
* Saiba como utilizar [tokens de acionadores de botões](introduction-to-button-trigger-tokens.md) para enviar dados atuais quando os fluxos de botões são executados.
* [Instalar a aplicação do Power Automate para Android](https://aka.ms/flowmobiledocsandroid).
* [Instalar a aplicação do Power Automate para iOS](https://aka.ms/flowmobiledocsios).

