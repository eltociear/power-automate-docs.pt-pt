---
title: Exemplo de partilha de imagens para partilhar fotografias | Microsoft Docs
description: Saiba como criar um Cartão Adaptável de partilha de fotografias.
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
ms.openlocfilehash: c804a65eee3b217dd2b6d66d54c7e39d87ef0eae
ms.sourcegitcommit: 3f582a1e462124d44f63cef7d450fc94be148f3b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/13/2020
ms.locfileid: "3372790"
---
# <a name="image-share-sample"></a>Exemplo de partilha de imagens 

O exemplo de **Formulário de Partilha de Imagens** é um Cartão Adaptável concebido para partilhar fotografias publicadas no SharePoint e que podem ser uma dependência de um processo a concluir (como processos relacionados com inspeção, conformidade e auditorias). Trata-se de um cartão adaptável apenas de visualização.

![Cartão adaptável apenas de visualização](media/adaptive-cards/image-share.png)

*Entradas/Saídas e notas*

| Nome do Token Dinâmico (entradas) | Texto do Marcador de Posição   | Notas                                              |
|-----------------------------|--------------------|-----------------------------------------------------|
| acphotoTitle                | {acphotoTitle}     | Texto a apresentar                                        |
| acTimestamp                 | {acTimestamp}      | Data/hora a apresentar                                   |
| acImageThumbnail            | {acImageThumbnail} | Imagem a apresentar <br>Deve ser substituído por um URL válido|
| acAltText                   | {acAltText}        | Texto alternativo de acessibilidade                      |

``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "{acphotoTitle}",
            "id": "Title",
            "size": "Large"
        },
        {
            "type": "TextBlock",
            "text": "{acTimestamp}",
            "size": "Medium",
            "weight": "Lighter"
        },
        {
            "type": "Image",
            "altText": "{acAltText}",
            "url": "{acImageThumbnail}"
        }
    ],
    "spacing": "None"
}
```


