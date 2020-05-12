---
title: Exemplo de gerador de sondagens | Microsoft Docs
description: Um formulário de entrada de Cartão Adaptável concebido para submeter sondagens ao Microsoft Teams.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/01/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b19a5b58db4680786ade089731846f0f8000d164
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297302"
---
# <a name="create-a-poll-sample"></a>Criar um exemplo de sondagem

O exemplo para **criar uma sondagem** é um formulário de entrada de Cartão Adaptável concebido para submeter sondagens ao Microsoft Teams. Substitua o texto a apresentar neste cartão para personalizar a sondagem. Este cartão adaptável permite-lhe utilizar diferentes caminhos de decisão com base nas respostas dadas nos valores da sondagem, ou nas contagens de votação, dos consumidores do cartão.

![Exemplo de sondagem](media/adaptive-cards/poll.png)

*Entradas/Saídas e notas*

| Nome do Token Dinâmico | Texto do Marcador de Posição | Notas:                                            |
|--------------------|------------------|---------------------------------------------------|
| Cargo              |                  | Texto a apresentar                                      |
| acHeaderTagLine    |                  | Texto a apresentar                                      |
| acHeader           |                  | Texto a apresentar                                      |
| acPollQuestion     |                  | Texto a apresentar                                      |
| acPollChoices      |                  | **Resultado** da resposta  <br> Seleção única como botões de opção|

``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Poll Request",
            "id": "Title",
            "spacing": "Medium",
            "horizontalAlignment": "Center",
            "size": "ExtraLarge",
            "weight": "Bolder",
            "color": "Accent"
        },
        {
            "type": "TextBlock",
            "text": "Header Tagline Text",
            "id": "acHeaderTagLine",
            "separator": true
        },
        {
            "type": "TextBlock",
            "text": "Poll Header",
            "weight": "Bolder",
            "size": "ExtraLarge",
            "spacing": "None",
            "id": "acHeader"
        },
        {
            "type": "TextBlock",
            "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer vestibulum lorem eget neque sollicitudin, quis malesuada felis ultrices. ",
            "id": "acInstructions",
            "wrap": true
        },
        {
            "type": "TextBlock",
            "text": "Poll Question",
            "id": "acPollQuestion"
        },
        {
            "type": "Input.ChoiceSet",
            "placeholder": "Select from these choices",
            "choices": [
                {
                    "title": "Choice 1",
                    "value": "Choice 1"
                },
                {
                    "title": "Choice 2",
                    "value": "Choice 2"
                },
                {
                    "title": "Choice 3",
                    "value": "Choice 3"
                }
            ],
            "id": "acPollChoices",
            "style": "expanded"
        }
    ],
    "actions": [
        {
            "type": "Action.Submit",
            "title": "Submit",
            "id": "btnSubmit"
        }
    ]
}
```


