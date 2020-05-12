---
title: Exemplo de cartão de atualização de metadados de Cartões Ajustáveis | Microsoft Docs
description: Notifique ou atualize os membros ou canais do Teams com metadados relacionados com um registo, ficheiro ou tópico.
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
ms.openlocfilehash: 902510ac5c2dd61fbcaae7c1dad771588e431873
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297654"
---
# <a name="metadata-update-card-sample"></a>Exemplo de cartão de atualização de metadados

O exemplo de **Atualização de Metadados** é um cartão ajustável concebido para permitir que os criadores de fluxos notifiquem ou atualizem os membros ou canais do Teams com metadados relacionados com um registo, ficheiro ou tópico. Trata-se de um cartão ajustável apenas de visualização. No entanto, poderão ser adicionados campos de entrada se for utilizada uma das ações *aguardar resposta* para o criar.

Este cartão é composto por três secções:

1. A área de cabeçalho do tópico com o cabeçalho, o subcabeçalho e a descrição.
1. A área da lista de factos dos metadados de registo relevantes.
1.  Um conjunto de colunas que suporta uma matriz de tabela de dados

![Exemplo de metadados](media/adaptive-cards/metadata-sample.png) 


*Entradas/Saídas e notas*

| Nome do Token Dinâmico (entradas) | Texto do Marcador de Posição    | Notas                                     |
|-----------------------------|---------------------|--------------------------------------------|
| acHeader                    | {Header}            | Texto a apresentar                               |
| acSubHeader                 | {SubHeader}         | Texto a apresentar                               |
| acDescription               | Texto em Latim          | Texto a apresentar                               |
| acFact1                     | {acFact1}           | Texto a apresentar                               |
| acFact2                     | {acFact2}           | Texto a apresentar                               |
| acFact3                     | {acFact3}           | Texto a apresentar                               |
| acColumnSetHeader           | Cabeçalhos 1 a 3 | Texto a apresentar <br>  Texto a apresentar do cabeçalho do conjunto de colunas                               |
| acColumnSet                 | Colunas 1 a 3 | Substituir pelos valores de matriz ou de coluna.       |


``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Metadata Update Card",
            "weight": "bolder",
            "size": "large",
            "id": "acTitle"
        },
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Sub Header Tag Line",
                            "weight": "Bolder",
                            "wrap": true,
                            "id": "acSubHeader"
                        }
                    ]
                }
            ]
        },
        {
            "type": "TextBlock",
            "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. In condimentum leo lorem, at facilisis augue hendrerit eget. Praesent ut malesuada ipsum. Vivamus semper faucibus felis quis sagittis. Nunc pellentesque metus at nunc gravida, vitae volutpat sapien vehicula. Nulla lorem nibh, porttitor vel semper ut, ornare nec erat.",
            "wrap": true,
            "id": "acDescriptionArea"
        },
        {
            "type": "FactSet",
            "facts": [
                {
                    "title": "Fact 1:",
                    "value": "{acFact1}"
                },
                {
                    "title": "Fact 2:",
                    "value": "{acFact2}"
                },
                {
                    "title": "Fact 3:",
                    "value": "{acFact3}"
                }
            ],
            "id": "acFactSet"
        },
        {
            "type": "Container",
            "spacing": "Large",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "weight": "Bolder",
                                    "text": "HEADER 1"
                                }
                            ],
                            "width": "stretch"
                        },
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "weight": "Bolder",
                                    "text": "HEADER 2"
                                }
                            ],
                            "width": "stretch"
                        },
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "weight": "Bolder",
                                    "text": "HEADER 3"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Column 1",
                            "wrap": true,
                            "id": "acCol1"
                        }
                    ],
                    "width": "stretch"
                },
                {
                    "type": "Column",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Column 2",
                            "wrap": true,
                            "id": "acCol2"
                        }
                    ],
                    "width": "stretch"
                },
                {
                    "type": "Column",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Column 3",
                            "wrap": true,
                            "id": "acCol4"
                        }
                    ],
                    "width": "stretch"
                }
            ],
            "$data": "acDataContext"
        }
    ],
    "bleed": true

}
```
