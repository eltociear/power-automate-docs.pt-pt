---
title: Utilizar Input Method Editors (IMEs) em fluxos de IU | Microsoft Docs
description: Saiba como utilizar Input Method Editors (IMEs) em fluxos de IU.
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
ms.date: 02/25/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 167f9321dba853e801102bed2ebe7e8902437d71
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298490"
---
# <a name="use-input-method-editors-imes-in-ui-flows"></a>Use Input Method Editors (IMEs) in UI flows (Utilizar Input Method Editors [IMEs] em fluxos de IU)

Pode utilizar a funcionalidade **Adicionar texto estático** para gravar as entradas de texto, em qualquer idioma, com IMEs ou teclados normais nos seus fluxos de IU. Utilize a opção **Adicionar texto estático** se quiser que a automatização insira o mesmo texto sempre que o seu fluxo de IU for executado. 

>[!TIP]
>Utilize a opção **Entrada de texto** se quiser utilizar texto dinâmico que muda sempre que o seu fluxo de IU é executado.

## <a name="invoke-ime"></a>Invocar o IME

Siga estes passos após começar a gravação e estará pronto para inserir entradas de texto estático:

1. Selecione o controlo onde pretende introduzir o texto estático.

   ![Selecione o controlo](../media/use-ime/select-control.png)

1. Selecione **Utilizar Entrada** no gravador e, em seguida, selecione **Adicionar texto estático**.

   ![Selecione Adicionar texto estático](../media/use-ime/add-static-text.png)

   Verá uma caixa de introdução para introduzir texto estático. Pode utilizar um teclado IME, inglês ou qualquer teclado internacional.

   ![Introduzir texto estático](../media/use-ime/enter-static-text.png)

1. Introduza o texto.

1. Selecione **Adicionar à aplicação** e, em seguida, selecione o controlo onde pretende introduzir o texto. Verá o texto inserido no controlo. 

   Este texto é introduzido automaticamente no momento da reprodução, mesmo que os computadores a reproduzir não tenham os mesmos esquemas de teclado ou que tenha sido utilizado IME na gravação.

   ![Reproduzir texto](../media/use-ime/playback-text.png)

   >[!TIP]
   >No estruturador Web, expanda a ação **Inserir entrada de texto** para rever ou editar o texto.

   ![Inserir entrada de texto](../media/use-ime/insert-text-input.png)


## <a name="use-the-replay-keystroke-action"></a>Utilizar a ação Repetir batimentos de tecla

Se tiver gravado entradas de texto sem a opção **Adicionar texto estático**, cada batimento de tecla é gravado e reproduzido por ordem cronológica. Isto inclui teclas especiais, como Ctrl, Alt, Tecla Windows, em qualquer esquema de teclado inglês ou internacional.

No estruturador, pode rever e editar as informações de gravação no formato [tecla virtual](https://docs.microsoft.com/windows/win32/inputdev/virtual-key-codes) na ação **Repetir batimentos de tecla**. 

![Tecla virtual](../media/use-ime/virtual-key.png)


> [!NOTE]
> Uma versão anterior do gravador de fluxos de IU utilizava as ações **SendKeys** e **PostElement**. Estas ações foram preteridas. Recomendamos que atualize para a versão mais recente do gravador de fluxos de IU e que volte a gravar os seus scripts para tirar vantagem das novas funcionalidades.

## <a name="troubleshooting-tips"></a>Dicas para resolução de problemas

1. Se gravar ações de teclado com o modo **Repetir batimentos de tecla**, tem de se certificar de que o computador de reprodução está a utilizar o mesmo teclado no momento da gravação, já que, com teclados diferentes, as mesmas sequências de repetição de batimentos de tecla poderão resultar em valores diferentes.

1. Só pode aplicar a ação **Utilizar entrada** a controlos do tipo de texto. Atualmente, a ação **Utilizar entrada** não consegue introduzir outros tipos de controlos, como caixa de combinação, menu pendente, ListView, etc.

## <a name="next-steps"></a>Passos seguintes

- Saiba como [configurar fluxos de IU](setup.md). 
- Saiba mais sobre os [diferentes tipos de fluxos](..\getting-started.md#types-of-flows) que pode utilizar para automatizar os seus fluxos de trabalho.


