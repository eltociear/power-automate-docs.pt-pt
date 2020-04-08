---
title: Saiba como editar os fluxos de IU para a Web | Microsoft Docs
description: Saiba como editar os fluxos de IU para a Web.
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 74c323f844c6bdc0f4cb1ad3d1a37977070a0a26
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/01/2020
ms.locfileid: "80525160"
---
# <a name="edit-web-ui-flows"></a>Editar fluxos de IU para a Web

Os fluxos de IU para a Web automatizam os sites em execução no [Microsoft Edge (versão 80 ou posterior)](https://www.microsoft.com/edge/) ou no Google Chrome. Depois de ter [criado um fluxo de IU para a Web](create-web.md), poderá precisar de o editar. Siga os passos neste documento para saber como editar os fluxos de IU para a Web.

## <a name="edit-in-selenium-ide"></a>Editar no IDE Selenium

Utilize o IDE Selenium para editar os fluxos de IU para a Web.

>[!NOTE]
>A edição no IDE Selenium destina-se a utilizadores e programadores avançados.

Pode consultar os [Selenium Commands](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) (Comandos do Selenium) para saber como editar o script.

O IDE Selenium sugere diferentes seletores e um seletor predefinido ao segmentar um elemento de interface de utilizador. Também pode definir um seletor novo se nenhum dos seletores propostos for adequado. Normalmente, esta situação acontece quando a estrutura de HTML do site é altamente dinâmica.

Veja a seguir um exemplo de seletores possíveis que o Selenium IDE identificou:

![Seletores possíveis](../media/edit-web/possible-selectors.png "Seletores possíveis")

## <a name="accessing-a-property-of-an-object-variable-or-item-of-an-array-variable"></a>Aceder a uma propriedade de uma variável de objeto ou item de uma variável de matriz**

Esta capacidade avançada permite-lhe utilizar sintaxes como \${foo.bar} para aceder à propriedade bar do objeto foo. Também é possível escrever para a propriedade bar do foo ao utilizar foo. bar como a propriedade value num comando store. Também pode utilizar sintaxes como \${foo[0]} para aceder ao item no índice 0 na matriz foo.

## <a name="next-steps"></a>Próximos passos

- [Criar os fluxos de IU para a Web](create-web.md)
- [Executar fluxos de IU](run-ui-flow.md)
