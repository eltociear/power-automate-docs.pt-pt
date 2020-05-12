---
title: Exemplo de comentários de candidatos | Microsoft Docs
description: Utilize este exemplo para criar um Cartão Adaptável para recolher comentários dos candidatos ao emprego.
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
ms.openlocfilehash: 0d0157c4e0d392dd8493e5aeca4e97531c95213d
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297280"
---
# <a name="candidate-feedback-sample"></a>Exemplo de comentários de candidatos

O exemplo de **formulário de comentários de candidatos** é um formulário de entrada de Cartão Adaptável concebido para recolher comentários durante um ciclo de entrevistas. É recomendável utilizá-lo com um botão de fluxo instantâneo partilhado para permitir que qualquer pessoa da equipa forneça comentários sobre os candidatos durante um ciclo de entrevistas. Expanda-o ao gravar as respostas numa base de dados ou outras origens de dados desejadas para suportar as seguintes oportunidades adicionais:

-   Facilitar a revisão das sugestões de acompanhamento antes da sessão seguinte com o candidato.
-   Facilitar a revisão dos dados agregados depois de todas as respostas serem gravadas.
-   Notificar o representante do departamento de Recursos Humanos da contagem de votos de contratação/não contratação no final do processo

     ![Formulário de comentários de candidatos](media/adaptive-cards/candidate-form.png)

*Entradas/Saídas e notas*

| Nome do Token Dinâmico | Texto do Marcador de Posição | Notas:              |
|--------------------|------------------|---------------------|
| {acFullName}       | {acFullName}     | Texto a apresentar        |
| {acComments}       | {acComments}     | Texto a apresentar        |
| {acDecision}       |                  | **Resultado** da resposta |
| {acFollowUp}       |                  | **Resultado** da resposta |

``` json
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.0",
  "body": [
    {
      "type": "TextBlock",
      "size": "Medium",
      "weight": "Bolder",      "id": "Title",
      "text": "CANDIDATE FEEDBACK FORM",
      "horizontalAlignment": "Left"
    },
    {
      "type": "Input.Text",
      "placeholder": "{acFullName}",
      "style": "text",
      "isMultiline": false,
      "maxLength": 75,
      "id": "acFullName"
    },
    {
      "type": "Input.Text",
      "placeholder": "{acComments}",
      "style": "text",
      "isMultiline": true,
      "maxLength": 200,
      "id": "acComments"
    },
    {
      "type": "TextBlock",
      "size": "Medium",
      "weight": "Bolder",
      "text": "Decision",
      "horizontalAlignment": "Left",
      "separator": true
    },
    {
      "type": "Input.ChoiceSet",
      "id": "acDecision",
      "value": "1",
      "choices": [
        {
          "title": "Hire",
          "value": "Hire"
        },
        {
          "title": "No Hire",
          "value": "No Hire"
        }
      ],
      "style": "expanded"
    },
    {
      "type": "TextBlock",
      "text": "Suggest follow-up discussion regarding:",
      "weight": "Bolder"
    },
    {
      "type": "Input.ChoiceSet",
      "id": "acFollowUp",
      "isMultiSelect": true,
      "value": "",
      "choices": [
        {
          "title": "Past experience in the topic area",
          "value": "Experience"
        },
        {
          "title": "Inclusive behaviors and work ethics",
          "value": "Inclusivity"
        },
        {
          "title": "Ability to work without supervision",
          "value": "Independent"
        }
      ]
    }
  ],
  "actions": [
    {
      "type": "Action.Submit",
      "title": "Submit"
    }
  ]
}
```


