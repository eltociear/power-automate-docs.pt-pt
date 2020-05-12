---
title: Aprenda a criar fluxos que publicam cartões adaptáveis no Microsoft Teams | Microsoft Docs
description: Aprenda a criar fluxos para publicar conteúdos com formatação avançada com cartões adaptáveis no Microsoft Teams.
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
ms.openlocfilehash: 3ba5f24bf24f57242441fab2770bce881bc78b69
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297390"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Utilizar cartões adaptáveis no Microsoft Teams


Pode criar um fluxo que publica [cartões adaptáveis](https://adaptivecards.io) num canal do Microsoft Teams. Com os cartões ajustáveis, pode utilizar a formatação avançada para tornar as publicações mais claras, interativas e interessantes. Os cartões ajustáveis podem conter componentes como imagens, gráficos, texto com formatação avançada e muito mais.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Criar um fluxo que publica cartões ajustáveis para uma equipa

Siga estes passos para criar um fluxo que publica um cartão ajustável no canal geral da equipa de Estratégia e Planeamento. O fluxo que criamos utiliza a ação **Publicar o seu próprio cartão ajustável como o bot do Flow num canal (pré-visualização)** para publicar semanalmente o conteúdo do cartão ajustável no canal da equipa.

1. Iniciar sessão no Microsoft Teams.
1. Selecione o ícone do **Teams** na barra de navegação à esquerda e, em seguida, selecione a equipa de **Estratégia e Planeamento**.

    ![Selecionar equipas](media/create-adaptive-cards-teams/select-teams-team.png)

1. Selecione o separador **Fluxo** na parte superior do ecrã.
1. Selecione o ícone **+** (Criar do zero).
1. Pesquise por **periodicidade** e, em seguida, selecione o acionador **Periodicidade**

    ![Cartão de periodicidade](media/create-adaptive-cards-teams/select-recurrence.png)

1. Defina o agendamento conforme indicado a seguir para repetir todas as semanas, numa hora e fuso horário da sua preferência:
    
    ![Cartão de periodicidade](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. Selecione **Novo passo**.
1. Pesquise por **adaptável**, selecione **Microsoft Teams** e, em seguida, selecione a ação **Publicar o seu próprio cartão adaptável como o bot do Flow num canal (pré-visualização)**.

   ![Cartão ajustável](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Indique uma **Equipa**, um **Canal** e uma **Mensagem** no cartão **Publicar o seu próprio cartão ajustável como o bot do Flow num canal (pré-visualização)** para indicar para que equipa e canal a **Mensagem** do cartão ajustável será publicada.

   ![Cartão ajustável](media/create-adaptive-cards-teams/adaptive-card-message.png)

   Pode utilizar este conteúdo JSON de exemplo para a **Mensagem**:

    ````
        {
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "speak": "Our team meeting is starting soon. Do you want to snooze  or do you want to send a late notification to the attendees?",
    "body": [
        {
        "type": "TextBlock",
        "text": "Strategy and Planning Weekly Team meeting",
        "size": "large",
        "weight": "bolder"
        },
        {
        "type": "TextBlock",
        "text": "Conf Room 112/3377 (10)",
        "isSubtle": true
        },
        {
        "type": "TextBlock",
        "text": "12:30 PM - 1:30 PM",
        "isSubtle": true,
        "spacing": "none"
        },
        {
        "type": "TextBlock",
        "text": "Snooze for"
        },
        {
        "type": "Input.ChoiceSet",
        "id": "snooze",
        "style": "compact",
        "value": "5",
        "choices": [
            {
            "title": "5 minutes",
            "value": "5",
            "isSelected": true
            },
            {
            "title": "15 minutes",
            "value": "15"
            },
            {
            "title": "30 minutes",
            "value": "30"
            }
        ]
        }
    ],
    "actions": [
        {
        "type": "Action.Submit",
        "title": "Snooze",
        "data": {
            "x": "snooze"
        }
        },
        {
        "type": "Action.Submit",
        "title": "I'll be late",
        "data": {
            "x": "late"
        }
        }
    ]
    }
    ````


1. Dê um nome ao fluxo e guarde-o.


## <a name="run-the-flow"></a>Executar o fluxo

Tenha em atenção que, depois de decorrido o tempo de periodicidade, o fluxo publica o conteúdo do cartão ajustável no canal da equipa que definiu.

![Executar o fluxo](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Mais Informações

- Comece a utilizar os [exemplos de cartão ajustável](https://adaptivecards.io/samples/).
- Crie [conteúdos de cartão ajustável](https://adaptivecards.io) da forma mais fácil.



