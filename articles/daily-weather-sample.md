---
title: Exemplo de relatório meteorológico diário de Cartões Adaptáveis | Microsoft Docs
description: Exemplo para criar um Cartão Adaptável para publicar uma atualização meteorológica diária num canal do Teams
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
ms.openlocfilehash: 8f7128104d3cb8aae361b6dd574822f503893e35
ms.sourcegitcommit: e3543e32e4e8e8163bef0565e27b657eabbdc741
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/10/2020
ms.locfileid: "75868187"
---
# <a name="daily-weather-report-sample"></a>Exemplo de relatório meteorológico diário

O exemplo de **relatório meteorológico diário** é um Cartão Adaptável concebido para ser utilizado com o MSN Meteorologia para publicar uma atualização meteorológica diária num canal do Teams.

![](media/adaptive-cards/weather.png)

*Entradas/Saídas e notas*

| Nome do Token Dinâmico     | Texto do Marcador de Posição | Notas                                                                         |
|------------------------|------------------|--------------------------------------------------------------------------------|
| {acCityState}          | Ver modelo     | Texto a apresentar <br>  Pode ser utilizada uma variável para manter os valores de Cidade, Distrito ou Código Postal                                                                   |
| {acDailySummary}       | Ver modelo     | Texto a apresentar                                                                   |
| {acCurrentDateTime}    | Ver modelo     | Texto a apresentar                                                                   |
| {acUrlConditionsImage} | Ver modelo     | Texto a apresentar  <br> Ver comentários do modelo Deve ser substituído por um URL válido                                                                 |
| {acCurrentTemperature} | Ver modelo     | Texto a apresentar                                                                   |
| {actempHi}             | Ver modelo     | Texto a apresentar                                                                   |
| {actempLow}            | Ver modelo     | Texto a apresentar                                                                   |


``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "{acCity}, {acState}",
            "size": "Large",
            "isSubtle": true
        },
        {
            "type": "TextBlock",
            "text": "{acCurrentDateTime}",
            "spacing": "None"
        },
        {
            "type": "TextBlock",
            "text": "{acDailySummary}",
            "spacing": "None"
        },
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "Image",
                            "url": "{acUrlConditionsImage}",
                            "size": "Large"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "{acCurrentTemperature}",
                            "size": "ExtraLarge",
                            "spacing": "None"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "stretch",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "°F",
                            "weight": "Bolder",
                            "spacing": "Small"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "stretch",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Hi {actempHi}",
                            "horizontalAlignment": "Left"
                        },
                        {
                            "type": "TextBlock",
                            "text": "Lo {actempLow}",
                            "horizontalAlignment": "Left",
                            "spacing": "None"
                        }
                    ]
                }
            ]
        }
    ]
}
```
