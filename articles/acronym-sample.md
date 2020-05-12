---
title: Exemplo de formulário de acrónimos de Cartões Adaptáveis | Microsoft Docs
description: Crie um cartão adaptável para recolher e armazenar acrónimos no Common Data Service.
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
ms.date: 01/04/2020
ms.author: deonhe
ms.openlocfilehash: b1ecc0240dba1866ea3468647d06637397d73170
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296510"
---
# <a name="acronyms-form-sample"></a>Exemplo de formulário de acrónimos

O exemplo de **formulário de acrónimos** é um formulário de entrada de Cartão Adaptável concebido para recolher e armazenar acrónimos no Common Data Service. Estes acrónimos podem ser consultados a partir de qualquer local devido a esta recolha de dados contínua.

![Logger de acrónimos](media/adaptive-cards/acronym-logger.png)

*Entradas/Saídas e notas*

| Nome do Token Dinâmico | Texto do Marcador de Posição                        | Notas:              |
|--------------------|-----------------------------------------|---------------------|
| {acAcronym}        | Introduza a abreviatura do acrónimo  | **Resultado** da resposta |
| {acDefinition}     | Introduza uma definição do acrónimo acima | **Resultado** da resposta |

``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Acronym Logger",
            "id": "Title",
            "spacing": "Medium",
            "horizontalAlignment": "Center",
            "size": "ExtraLarge",
            "weight": "Bolder",
            "color": "Accent"
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "TextBlock",
                    "text": "Acronym",
                    "wrap": true,
                    "spacing": "Medium"
                },
                {
                    "type": "Input.Text",
                    "id": "acAcronym",
                    "placeholder": "Enter the abbreviation for the acronym"
                },
                {
                    "type": "TextBlock",
                    "text": "Definition",
                    "wrap": true
                },
                {
                    "type": "Input.Text",
                    "placeholder": "Enter a definition of the acronym above",
                    "id": "acDefinition",
                    "isMultiline": true
                }
            ]
        }
    ],
    "actions": [
        {
            "type": "Action.Submit",
            "title": "Submit",            "id": "btnSubmit"
        }
    ]
}

```