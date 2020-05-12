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
ms.date: 03/30/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8ea8301c1b50502995cc5081d960df44859458eb
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/01/2020
ms.locfileid: "3298710"
---
# <a name="use-inputs-and-outputs-in-web-ui-flows"></a>Utilizar entradas e saídas em fluxos de IU para a Web

Pode definir entradas a transmitir para as suas aplicações automatizadas durante a reprodução. Também pode transmitir *saídas* das suas aplicações automatizadas para o seu fluxo.

## <a name="define-inputs-for-a-web-ui-flow"></a>Definir entradas para um fluxo de IU para a Web

As entradas de um fluxo de IU permitem transmitir informações de uma origem externa, como uma base de dados ou outro fluxo de IU, para o software herdado de destino que vai automatizar.

Qualquer variável utilizada (lida) antes da inicialização (normalmente feita através de comandos **store**) será automaticamente tratada como uma variável de entrada e será apresentada no cartão da ação **Executar um fluxo de IU para a Web**.

Pode utilizar variáveis através da interpolação de cadeias, por exemplo, altere o campo de destino do comando clique para "id=\${elementId}". Ou altere o campo de valor do tipo de comando para "\${inputText}".

O comando **set window size** e o comando **type** presentes nas capturas de ecrã seguintes utilizam variáveis não inicializadas \${Width}, \${Height} e \${search}. Estas variáveis tornar-se-ão valores de entrada.

![Set window size e type](../media/inputs-outputs-web/set-window-size.png "Set window size e type")

Pode utilizar variáveis diretamente em alguns comandos, por exemplo, os campos target/value do comando forEach são variáveis; não precisa de os colocar entre “\${}”.

Consulte a referência [Selenium commands](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) (Comandos do Selenium) para determinar quais são os comandos que assumem nomes de variável diretamente.

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

## <a name="next-steps"></a>Passos seguintes

- Saiba como [criar fluxos de IU para a Web](create-web.md).
- Saiba como [acionar fluxos de IU](run-ui-flow.md).

