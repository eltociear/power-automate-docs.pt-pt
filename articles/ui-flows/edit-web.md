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
ms.openlocfilehash: f29873dff5ae842d2f7b86f4f6e3e5c31bf04712
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74371693"
---
# <a name="edit-web-ui-flows"></a>Editar fluxos de IU para a Web

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Os fluxos de IU para a Web automatizam os sites em execução na [próxima versão do Microsoft Edge](https://www.microsoftedgeinsider.com/) ou no Google Chrome. Depois de ter [criado um fluxo de IU para a Web](create-web.md), poderá precisar de o editar. Siga os passos neste documento para saber como editar os fluxos de IU para a Web.

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

## <a name="next-steps"></a>Passos seguintes

- [Criar os fluxos de IU para a Web](create-web.md)
- [Executar fluxos de IU](run-ui-flow.md)
