---
title: Exemplo de recolha de oportunidades potenciais | Microsoft Docs
description: Crie um Cartão Adaptável para recolher oportunidades potenciais de pessoas interessadas num conjunto de produtos.
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
ms.openlocfilehash: 6ec875a8a3bf682b7a3d9b44a0cc1d3624bf7a70
ms.sourcegitcommit: 0761c15339ba3de6036f7fe5251aa8ad9173ee8b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902213"
---
# <a name="lead-collection-sample"></a>Exemplo de recolha de oportunidades potenciais

O exemplo de **recolha de oportunidades potenciais** é um formulário de entrada de Cartão Adaptável concebido para recolher oportunidades potenciais de qualquer pessoa que possa entrar em contacto com alguém interessado num conjunto de produtos. Sinta-se à vontade para alterar as opções dos produtos, mas não se esqueça de que cada opção pode ter texto a apresentar, bem como um valor interno que será gerado depois de alguém submeter o cartão (também pode ser o mesmo mostrado no bloco de código de exemplo).

![](media/adaptive-cards/lead-notification.png)

*Entradas/Saídas e notas:*

| Nome do Token Dinâmico    | Texto do Marcador de Posição       | Notas                                                                                       |
|-----------------------|------------------------|--------------------------------------|
| Título                 |                        | Texto a apresentar                                                                                  |
| acInstructions        |                        | Texto a apresentar                                                                                  |
| acLeadFName           | {firstName}            | **Resultado** da resposta                                                                           |
| acLeadLName           | {lastName}             | **Resultado** da resposta                                                                           |
| acLeadEmail           | {emailAddress}         | **Resultado** da resposta                                                                           |
| acLeadPrimaryPhone    | {primaryPhone10digits} | **Resultado** da resposta                                                                           |
| acLeadProductInterest | {productInterests}     | **Resultado** da resposta  <br>Tal como os valores de seleção múltipla, em que cada seleção será separada por uma vírgula.                                                                         |

``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "width": 2,
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Lead Notification",
                            "weight": "Bolder",
                            "id": "Title",
                            "size": "ExtraLarge"
                        },
                        {
                            "type": "TextBlock",
                            "text": "Please fill out a single form for each individual expressing interest in our products. ",
                            "isSubtle": true,
                            "wrap": true,
                            "id": "acInstructions",
                            "size": "Large"
                        }
                    ]
                }
            ]
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "TextBlock",
                    "text": "Potential Customer FIRST NAME",
                    "wrap": true,
                    "size": "Medium"
                }
            ]
        },
        {
            "type": "Input.Text",
            "id": "acLeadFName",
            "placeholder": "{firstName}"
        },
        {
            "type": "TextBlock",
            "text": "Potential Customer LAST NAME",
            "wrap": true
        },
        {
            "type": "Input.Text",
            "id": "acLeadLName",
            "placeholder": "{lastName}"
        },
        {
            "type": "TextBlock",
            "text": "Corporate email",
            "wrap": true
        },
        {
            "type": "Input.Text",
            "id": "acLeadEmail",
            "placeholder": "{emailAddress}",
            "style": "Email"
        },
        {
            "type": "TextBlock",
            "text": "Business Phone Number"
        },
        {
            "type": "Input.Text",
            "id": "acLeadPrimaryPhone",
            "placeholder": "{primaryPhone10digits}",
            "style": "Tel"
        },
        {
            "type": "RichTextBlock",
            "inlines": [
                {
                    "type": "TextRun",
                    "text": "{productInterests}"
                }
            ]
        },
        {
            "type": "Input.ChoiceSet",
            "placeholder": "Placeholder text",
            "choices": [
                {
                    "title": "Office 365",
                    "value": "Office 365"
                },
                {
                    "title": "Dynamics 365",
                    "value": "Dynamics 365"
                },
                {
                    "title": "Azure Services",
                    "value": "Azure Services"
                },
                {
                    "title": "Power Platform",
                    "value": "Power Platform"
                }
            ],
            "style": "expanded",
            "id": "acLeadProductInterest",
            "isMultiSelect": true
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


