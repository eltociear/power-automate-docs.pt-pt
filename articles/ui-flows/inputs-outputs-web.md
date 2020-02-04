---
title: Utilizar entradas e saídas em fluxos de IU para a Web | Microsoft Docs
description: Utilizar entradas e saídas em fluxos de IU para a Web.
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
ms.openlocfilehash: 38b6ba7f8fe3ab7a386229b6c9c5ccc300a147de
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74371417"
---
# <a name="use-inputs-and-outputs-in-web-ui-flows"></a>Utilizar entradas e saídas em fluxos de IU para a Web

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs-for-a-web-ui-flow"></a>Definir entradas para um fluxo de IU para a Web

As entradas de um fluxo de IU permitem transmitir informações de uma origem externa, como uma base de dados ou outro fluxo de IU, para o software herdado de destino que vai automatizar.

Qualquer variável utilizada (lida) antes da inicialização (normalmente feita através de comandos **store**) será automaticamente tratada como uma variável de entrada e será apresentada no cartão da ação **Executar um fluxo de IU para a Web**.

Pode utilizar variáveis através da interpolação de cadeias, por exemplo, altere o campo target do comando click para “id=\${elementId}”. Ou altere o campo value do comando type para “\${inputText}”.

O comando **set window size** e o comando **type** presentes nas capturas de ecrã seguintes utilizam variáveis não inicializadas \${Width}, \${Height} e \${search}. Estas variáveis tornar-se-ão valores de entrada.

![Set window size e type](../media/inputs-outputs-web/f05cb445dad212aaf395b66ba969622c.png "Set window size e type")

Pode utilizar variáveis diretamente em alguns comandos, por exemplo, os campos target/value do comando forEach são variáveis; não precisa de os colocar entre “\${}”.

Consulte a referência [Selenium commands](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) (Comandos do Selenium) para determinar quais os comandos que assumem o nome da variável diretamente.

## <a name="define-outputs-for-a-web-ui-flow"></a>Definir saídas para um fluxo de IU para a Web

Qualquer variável definida no script do selenium torna-se automaticamente num valor de saída. Utilize os seguintes comandos para declarar variáveis:

[Store](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store)

[Store attribute](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-attribute)

[Store json](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-json)

[Store title](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-title)

[store value](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-value)

[Store window handle](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-window-handle)

[Store xpath count](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-xpath-count)

[Execute script](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#execute-script) (adicione a sintaxe “return” para devolver o objeto que quer armazenar no fim do script)

## <a name="next-steps"></a>Próximos passos

- Saiba como [criar fluxos de IU para a Web](create-web.md).
- Saiba como [acionar fluxos de IU](run-ui-flow.md).

