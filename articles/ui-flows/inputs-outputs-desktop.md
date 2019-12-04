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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 391e977343617497328ff231d4808a0c78ceb154
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74371647"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Utilizar entradas e saídas em fluxos de IU para computador

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs"></a>Definir entradas

As entradas permitem transmitir informações de uma origem externa, como uma base de dados ou qualquer conector suportado, para o software herdado que os fluxos de IU automatizam.

Por exemplo, pode utilizar as informações de clientes de uma lista do SharePoint como uma origem para a entrada no software de gestão contabilística herdado.

### <a name="define-inputs-in-the-ui-flows-wizard"></a>Definir entradas no assistente de fluxos de IU

1. Selecione “Nova entrada”

   ![](../media/inputs-outputs-desktop/2eb6313a0e966f1fbfc352445b89ee39.png)

1. Adicione um nome, dados de exemplo e uma descrição à entrada.

    - Os dados de exemplo são utilizados durante a gravação ou o teste.

    - A descrição será útil para diferenciar as entradas que criou.

   ![](../media/inputs-outputs-desktop/e33d206bf2158228277a276261c49785.png)

1.  Depois de as entradas terem sido criadas, pode clicar em seguinte para as utilizar numa gravação.

### <a name="use-inputs-to-pass-information-to-the-application"></a>Utilizar entradas para transmitir informações para a aplicação

1. Durante a gravação, pode utilizar uma entrada numa aplicação ao selecionar **Utilizar entrada**.

1. Na lista, pode escolher entre três opções:

    - Selecione uma das entradas que definiu no passo **Configurar campos de texto** dos fluxos de IU.

    - Utilize uma saída definida anteriormente (veja a secção Saídas). Pode útil para transmitir informações entre diferentes aplicações dentro do mesmo fluxo de IU.

    - Crie uma nova entrada enquanto estiver a gravar. Vai encontrá-la no passo **Configurar campos de texto** dos fluxos de IU.

   ![](../media/inputs-outputs-desktop/de36baa0f85d5a19304e1606de25aa3e.png)

1. Selecione a localização onde quer utilizar a entrada. O valor de exemplo que definiu será automaticamente utilizado. No exemplo abaixo, “Hello world” é o valor de exemplo para o nome da entrada “A minha entrada” e é adicionado à página no Microsoft Word.  
    
    ![](../media/inputs-outputs-desktop/d6b74dc86f38c51cf1daa0582ff0cc33.png)

1. No Power Automate em **Gravar e editar passos**, expanda as ações que utilizam entradas para ver qual delas foi selecionada.

   ![](../media/inputs-outputs-desktop/340aa71942b618431b0455b632f76f52.png)

1. Quando aciona o fluxo de IU, pode alterar o valor da entrada conforme desejar. Para obter mais informações, veja Utilizar entradas e saídas.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Utilizar saídas para extrair informações da aplicação

As saídas permitem transmitir informações a partir do software herdado que os fluxos de IU automatizam para um destino externo, como uma base de dados ou qualquer [conector suportado](https://flow.microsoft.com/connectors/).

Por exemplo, pode extrair informações de clientes do software de gestão contabilística herdado e adicioná-las a uma lista do SharePoint.

As saídas só podem ser criadas à medida que grava o fluxo de IU.

1. Durante uma gravação, selecione no gravador o botão “Obter saída”.

   ![](../media/inputs-outputs-desktop/13f8dfca19c0ed04ca2a0f87bf7055ea.png)

1. Selecione o botão “Selecionar texto” (este é o único tipo de saída disponível por agora).

   ![](../media/inputs-outputs-desktop/2845b73ee807a5be747c1dc494570ab7.png)

1. Clique num elemento da Interface de Utilizador para selecionar o texto da saída. O valor será capturado automaticamente.

   ![](../media/inputs-outputs-desktop/7df19b56aadcd0aef207c7372a04b3c6.png)

   ![](../media/inputs-outputs-desktop/af55a0bf39d805b154a783eff3de131b.png)

1. Defina o nome e a descrição da saída.

   ![](../media/inputs-outputs-desktop/a083579ee011dfb76aa21fac116796a3.png)

1. Selecione **Guardar**. 

A saída está agora disponível na área dedicada do assistente

   ![](../media/inputs-outputs-desktop/b9f396de0b5893c5a3152b592911f67a.png)

Cada saída tem:

-  Um nome de saída conforme definido durante a gravação
-  Uma descrição: este campo pode ser muito útil quando define várias saídas durante uma gravação e deseja identificá-las facilmente.
-  Um nome de ação: a ação onde a saída foi definida no fluxo de IU

## <a name="delete-an-output-from-a-ui-flow"></a>Eliminar uma saída de um fluxo de IU

Se deixar de precisar de uma saída, poderá eliminá-la ao voltar à ação associada e remover o Nome da saída no valor dinâmico.

## <a name="test-your-ui-flow"></a>Testar o fluxo de IU

Testar fluxos de IU permite-lhe validar as alterações e o comportamento de reprodução adequado.

1. (Opcional) Introduza um novo valor no campo de texto. 
    
    ![](../media/inputs-outputs-desktop/0b4aef639c4ab30b93413e1e7a5e662d.png)

1. Clique em **Testar agora** para ver o software herdado que está a ser automatizado. Verá a automatização de fluxo de IU reproduzir os passos que gravou. **Não interaja com o dispositivo durante a reprodução.**

1. Depois de a reprodução ter sido concluída, verá o estado de execução do fluxo de IU:

    - Para cada ação, um estado que indica que o teste funcionou bem e as entradas associadas.

    - O valor das saídas obtidas para este teste.

    - Caso tenha sido gerado um erro, poderá ver qual dos passos foi problemático com uma captura de ecrã do momento em que o erro ocorreu.

   ![](../media/inputs-outputs-desktop/85056d7942d12a5408005f5b683d432b.png)

## <a name="learn-more"></a>Saiba mais

- Saiba como [acionar o fluxo de IU](run-ui-flow.md) que acabou de criar.

- Se quiser fazer mais com os fluxos de IU, poderá também experimentar os fluxos de IU com parâmetros de [entrada e saída](inputs-outputs-web.md).


