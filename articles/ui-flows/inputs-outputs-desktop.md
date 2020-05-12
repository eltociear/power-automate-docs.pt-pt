---
title: Utilizar entradas e saídas em fluxos de IU para computador | Microsoft Docs
description: Utilizar entradas e saídas em fluxos de IU para computador.
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
ms.date: 03/24/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: fd4200c98df4a60318b5d95ab590d4ec59e6bef3
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/01/2020
ms.locfileid: "3298798"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Utilizar entradas e saídas em fluxos de IU para computador

Utilize entradas para transmitir informações de uma origem externa, como uma base de dados ou qualquer conector suportado, para o software herdado que os fluxos de IU automatizam.

Por exemplo, pode utilizar as informações de clientes de uma lista do SharePoint como uma origem para a entrada no software de gestão contabilística herdado.

## <a name="define-inputs-in-the-ui-flows-wizard"></a>Definir entradas no assistente de fluxos de IU

1. Selecione **Nova entrada**.

   ![Selecionar nova](../media/inputs-outputs-desktop/select-new.png)

1. Adicione um nome, dados de exemplo e uma descrição à entrada.

    - Os dados de exemplo são utilizados durante a gravação ou o teste.

    - A descrição será útil para diferenciar as entradas que criou.

   ![Campos de entrada](../media/inputs-outputs-desktop/input-fields.png)

1.  Depois de as entradas terem sido criadas, pode clicar em seguinte para as utilizar numa gravação.

>[!TIP]
>Pode utilizar a combinação de teclas **Ctrl+Alt+L** para inserir texto que pode transmitir para ou a partir da aplicação que está a ser utilizada no fluxo de IU. Esta combinação de teclas funciona para texto sensível, estático, de saída e de entrada. 

## <a name="use-inputs-to-pass-information-to-the-application"></a>Utilizar entradas para transmitir informações para a aplicação

1. Durante a gravação, pode utilizar uma entrada numa aplicação ao selecionar **Utilizar entrada**.

1. Na lista, pode escolher entre três opções:

    - Selecione uma das entradas que definiu no passo **Configurar campos de entrada**.

    - Utilize uma saída definida anteriormente (veja a secção Saídas). Pode útil para transmitir informações entre diferentes aplicações dentro do mesmo fluxo de IU.

    - Crie uma nova entrada enquanto estiver a gravar. Vai encontrá-la no passo **Configurar campos de entrada**.

   ![Selecionar o tipo de entrada](../media/inputs-outputs-desktop/select-input-type.png)

1. Selecione a localização onde quer utilizar a entrada. O valor de exemplo que definiu será automaticamente utilizado. No exemplo abaixo, “Hello world” é o valor de exemplo para o nome da entrada “A minha entrada” e é adicionado à página no Microsoft Word.  
    
    ![Selecionar a localização para entrada](../media/inputs-outputs-desktop/select-location-for-input.png)

1. No Power Automate, em **Gravar e editar passos**, expanda as ações que utilizam entradas para ver qual delas está selecionada.

   ![Expandir ações](../media/inputs-outputs-desktop/expand-actions.png)

1. Quando aciona o fluxo de IU, pode alterar o valor da entrada conforme desejar.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Utilizar saídas para extrair informações da aplicação

As saídas permitem transmitir informações a partir do software herdado que os fluxos de IU automatizam para um destino externo, como uma base de dados ou qualquer [conector suportado](https://flow.microsoft.com/connectors/).

Por exemplo, pode extrair informações de clientes do software de gestão contabilística herdado e adicioná-las a uma lista do SharePoint.

As saídas só podem ser criadas à medida que grava o fluxo de IU.

1. Durante uma gravação, selecione **Obter saída**.

   ![Obter saída](../media/inputs-outputs-desktop/get-output.png)

1. Selecione **Selecionar texto**.

   ![Selecionar texto](../media/inputs-outputs-desktop/select-text.png)

1. Selecione um elemento da interface de utilizador para obter o texto da saída. O valor de texto será capturado automaticamente.

   <!-- ![Get element output](../media/inputs-outputs-desktop/get-element-output.png) -->

   ![Selecionar o elemento da IU](../media/inputs-outputs-desktop/select-ui-element.png)

1. Forneça um nome e uma descrição para a saída.

   ![Fornecer um nome e uma descrição](../media/inputs-outputs-desktop/name-description.png)

1. Selecione **Guardar**. 

A sua saída está agora disponível na área dedicada do assistente.

   ![A saída está disponível](../media/inputs-outputs-desktop/output-available.png)

Cada saída tem:

-  Um nome de saída conforme definido durante a gravação.
-  Uma descrição: este campo pode ser muito útil quando define várias saídas durante uma gravação e deseja identificá-las facilmente mais tarde.
-  Um nome de ação: a ação na qual a saída está definida no fluxo de IU.

## <a name="delete-an-output-from-a-ui-flow"></a>Eliminar uma saída de um fluxo de IU

Se deixar de precisar de uma saída, elimine-a ao voltar à ação associada e remover o nome da saída no valor dinâmico.

## <a name="test-your-ui-flow"></a>Testar o fluxo de IU

Testar fluxos de IU permite-lhe validar as alterações e o comportamento de reprodução adequado.

1. (Opcional) Introduza um novo valor no campo de texto. 
    
    ![Novo valor de teste](../media/inputs-outputs-desktop/new-test-value.png)

1. Clique em **Testar agora** para ver o software herdado que está a ser automatizado. Verá a automatização de fluxo de IU reproduzir os passos que gravou. **Não interaja com o dispositivo durante a reprodução.**

1. Quando a reprodução terminar, verá o estado da execução do seu fluxo de IU:

    - Para cada ação, um indicador de estado que mostra que o teste funcionou bem, assim como as entradas associadas.

    - O valor das saídas obtidas para este teste.

    - Se ocorrer um erro, verá o passo que causou o problema com uma captura de ecrã do momento em que o erro ocorreu.

   ![Uma execução bem-sucedida](../media/inputs-outputs-desktop/successful-run.png)

## <a name="learn-more"></a>Mais Informações

- Saiba como [acionar fluxos de IU](run-ui-flow.md).



