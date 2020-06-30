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
ms.openlocfilehash: bf7f21915b63087911edbdbbe181bb5073ffbfb9
ms.sourcegitcommit: aefd1ebedfbd8c6cc3d08397ac171cb4ba5b5315
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/30/2020
ms.locfileid: "3412940"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Utilizar entradas e saídas em fluxos de IU para computador

Utilize entradas para transmitir informações de uma origem externa, como uma base de dados ou qualquer conector suportado, para o software herdado que os fluxos de IU automatizam.

Por exemplo, pode utilizar as informações de clientes de uma lista do SharePoint como uma origem para a entrada no software de gestão contabilística herdado. Também pode passar entradas sensíveis como um nome de utilizador ou uma palavra-passe que são necessárias para iniciar sessão numa aplicação antiga utilizando **Entradas de texto sensível**.

## <a name="define-inputs-in-the-ui-flows"></a>Definir entradas nos fluxos de IU

1. Selecione **Texto** para definir uma entrada ou selecione **Texto sensível** para definir uma entrada de texto sensível. 

   ![Selecione novo.](../media/inputs-outputs-desktop/text-input.png)

1. Adicione um nome, dados de exemplo e uma descrição à entrada.

    - Os dados de exemplo são utilizados durante a gravação ou o teste.

    - A descrição será útil para diferenciar as entradas que criou.

    - Para entradas de texto sensível, o valor da amostra será ocultado e não será persistido depois de guardar

   ![Campos de entrada](../media/inputs-outputs-desktop/text-input.png)

1.  Depois das entradas terem sido criadas, pode clicar em Seguinte para as utilizar numa gravação.

>[!TIP]
>Pode utilizar a combinação de teclas **Ctrl+Alt+L** para inserir texto que pode transmitir para ou a partir da aplicação que está a ser utilizada no fluxo de IU. Esta combinação de teclas funciona para texto sensível, estático, de saída e de entrada. 

## <a name="use-inputs-to-pass-information-to-the-application"></a>Utilizar entradas para transmitir informações para a aplicação

1. Durante a gravação, pode utilizar uma entrada numa aplicação ao selecionar **Utilizar Entradas**.

1. Na lista, pode escolher entre três opções:

    - Selecione uma das entradas que definiu no passo **Configurar entradas**.

      >[!TIP]
      >Pode identificar facilmente entradas de texto sensível porque têm um ícone diferente das entradas de texto.

    - Utilize uma saída definida anteriormente (veja a secção Saídas). Pode útil para transmitir informações entre diferentes aplicações dentro do mesmo fluxo de IU.

    - Crie um novo texto ou entrada de texto sensível à medida que estiver a gravar utilizando a nova opção de **Entrada**. Vai encontrá-la no passo **Configurar entrada**.

   ![Selecionar o tipo de entrada](../media/inputs-outputs-desktop/select-input-type.png)

1. Selecione a localização onde quer utilizar a entrada. O valor de exemplo que definiu será automaticamente utilizado. No exemplo abaixo, “WingTip Toys” é o valor de exemplo para o nome da entrada “Conta de Faturação” e é adicionado à aplicação.  
    
    ![Selecionar a localização para entrada](../media/inputs-outputs-desktop/select-location-for-input.png)

1. No Power Automate, em **Gravar e editar passos**, expanda as ações que utilizam entradas para ver qual delas está selecionada.

    No exemplo que se segue, verá que a "Conta de Faturação" é usada como valor.

   ![Expandir ações](../media/inputs-outputs-desktop/expand-actions.png)


   >[!NOTE]
   >Se também utilizou uma entrada de texto sensível, veria uma ação com um ícone de bloqueio no canto direito superior para indicar que utilizou a entrada de texto sensível.


   ![Expandir ações](../media/inputs-outputs-desktop/lock-action.png)

1. Quando aciona o fluxo de IU, pode alterar o valor da entrada conforme desejar.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Utilizar saídas para extrair informações da aplicação

As saídas permitem transmitir informações a partir do software herdado que os fluxos de IU automatizam para um destino externo, como uma base de dados ou qualquer [conector suportado](https://flow.microsoft.com/connectors/).

Por exemplo, pode extrair informações de clientes do software de gestão contabilística herdado e adicioná-las a uma lista do SharePoint.

As saídas só podem ser criadas à medida que grava o fluxo de IU.

1. Durante uma gravação, selecione **Saída**.

   ![Obter saída](../media/inputs-outputs-desktop/get-output.png)

1. Selecione **Selecionar texto**.

   ![Selecionar texto](../media/inputs-outputs-desktop/select-text.png)

1. Selecione um elemento da interface de utilizador para obter o texto da saída. O valor de texto será capturado automaticamente. Pode fornecer um nome e uma descrição para a saída.

   ![Selecionar o elemento da IU](../media/inputs-outputs-desktop/select-ui-element.png)

1. Forneça um nome e uma descrição para a saída.

1. Selecione **Guardar**. 

A sua saída está agora disponível na área dedicada do assistente.

   ![A saída está disponível](../media/inputs-outputs-desktop/output-available.png)

Cada saída tem:

-  Um nome de saída conforme definido durante a gravação.
-  Uma descrição: este campo pode ser muito útil quando define várias saídas durante uma gravação e deseja identificá-las facilmente mais tarde.
-  Um nome de ação: a ação na qual a saída está definida no fluxo de IU.

## <a name="use-clipboard-content-to-define-outputs"></a>Utilize conteúdo de área de transferência para definir saídas 

Durante uma gravação, é possível copiar um texto na área de transferência do seu computador e defini-lo como saída do seu fluxo de IU.

1. Durante a sua gravação, copie um valor de cadeia  

1. Selecione **Obter texto da Área de Transferência**. O conteúdo da sua área de transferência é apresentado no campo **Valor de exemplo** 

   ![Saída da área de transferência](../media/inputs-outputs-desktop/get-output-clipboard.png)

1. Defina um nome e uma descrição para a sua saída (como descrito acima) e selecione **Guardar.** 

    ![Saída da área de transferência](../media/inputs-outputs-desktop/get-output-clipboard-2.png)

## <a name="delete-an-output-from-a-ui-flow"></a>Eliminar uma saída de um fluxo de IU

Se deixar de precisar de uma saída, elimine-a ao voltar à ação associada e remover o nome da saída no valor dinâmico.

## <a name="test-your-ui-flow"></a>Testar o fluxo de IU

Testar fluxos de IU permite-lhe validar as alterações e o comportamento de reprodução adequado.

1. (Opcional) Introduza um valor no campo de texto. 

   >[!NOTE]
   >Para quaisquer entradas de texto sensível que sejam criadas no gravador, o valor da amostra terá de ser especificado novamente antes de testar.
    
    ![Novo valor de teste](../media/inputs-outputs-desktop/new-test-value.png)

1. Selecione **Testar agora** para ver o software herdado que está a ser automatizado. Verá a automatização de fluxo de IU reproduzir os passos que gravou. **Não interaja com o dispositivo durante a reprodução.**

1. Quando a reprodução terminar, verá o estado da execução do seu fluxo de IU:

    - Para cada ação, um indicador de estado que mostra que o teste funcionou bem, assim como as entradas associadas.

      ![Uma execução bem-sucedida](../media/inputs-outputs-desktop/successful-run.png)

   - Para cada ação que utilize uma entrada de **Texto sensível**, o valor de entrada não será apresentado.

      ![Outra imagem](../media/inputs-outputs-desktop/sensitive-text-not-displayed.png)

   - Também verá o valor das saídas obtidas para este teste na parte inferior do estruturador. 

      ![Outra imagem](../media/inputs-outputs-desktop/outputs-value.png)

   - Se ocorrer um erro, verá o passo que causou o problema juntamente com uma captura de ecrã do momento em que o erro ocorreu.

## <a name="learn-more"></a>Mais Informações

- Saiba como [acionar fluxos de IU](run-ui-flow.md).



