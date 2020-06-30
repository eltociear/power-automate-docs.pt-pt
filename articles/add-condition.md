---
title: Adicionar uma condição a um fluxo | Microsoft Docs
description: Especifique que um fluxo efetua uma ou mais tarefas, apenas se uma condição for verdadeira.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/08/2020
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c717bfcb10fdae3da5d1a3642ece503ad3de4389
ms.sourcegitcommit: 549224cf13fc761f473c880e8d0d8f2741cc7b0f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/08/2020
ms.locfileid: "3434998"
---
# <a name="add-a-condition-to-a-flow"></a>Adicionar uma condição a um fluxo


Especifique que um fluxo efetua uma ou mais tarefas, apenas se uma condição for verdadeira. Especifique, por exemplo, que obterá uma mensagem de e-mail apenas se um tweet que contém uma palavra-chave for reenviado pelo menos 10 vezes.

## <a name="prerequisites"></a>Pré-requisitos

* [Criar um fluxo](get-started-logic-template.md) a partir de um modelo - este tutorial [utiliza este modelo](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) como exemplo

## <a name="add-a-condition"></a>Adicionar uma condição

1. No [Power Automate](https://flow.microsoft.com), selecione **Os meus fluxos**.

    Poderá ter de iniciar sessão, se ainda não o tiver feito.

1. Selecione um dos fluxos a partir de **Os meus fluxos** e, em seguida, selecione **Mais comandos** (os três pontos).

   ![Selecionar Editar](./media/add-condition/select-edit.png)

    Este tutorial utiliza um exemplo com um acionador do Twitter e uma ação do SharePoint.

1. Selecione **Editar**.

1. Por baixo da última ação, selecione **Novo passo** > **Condição**.

1. No cartão **Condição**, selecione uma área vazia na caixa à esquerda.

    A lista **Conteúdo dinâmico** é aberta.

1. Selecione o parâmetro **Contagem de tweets reenviados** para adicioná-lo à caixa.

1. Na caixa ao meio do cartão **Condição**, selecione **é maior ou igual a**.

1. Na caixa à direita, introduza **10**.

    ![A caixa OBJECT NAME com um parâmetro nela](./media/add-condition/specify-condition.png)

    Agora que configurou a condição, continue com os seguintes passos para enviar um e-mail se a **Contagem de tweets reenviados** for superior a 10.

1. Selecione **Adicionar uma ação** no envio **Se sim** da condição. 
1. Introduza **Enviar um e-mail** na caixa de pesquisa e selecione **Enviar um e-mail (V2)**.

   ![Procurar para enviar um e-mail](./media/add-condition/if-yes-condition.png)

1. Configure o cartão **Enviar um e-mail (V2)** ao seu gosto, indicando os conteúdos do e-mail que o fluxo envia se a **Contagem de tweets reenviados** for maior que 10.

   Também pode configurar o lado **Se não** da condição se pretende um momento quando a **Contagem de tweets reenviados** for menor que 10.

1. Guarde o fluxo.

>[!TIP]
>Poderá criar condições complexas através do botão **Adicionar** no cartão de condição.

![Adicionar condições complexas](./media/add-condition/add-complex-condition.png)

Pode utilizar qualquer expressão da *Linguagem de definição do fluxo de trabalho* em modo avançado. Saiba mais sobre todas as [expressões](https://msdn.microsoft.com/library/azure/mt643789.aspx) disponíveis.

## <a name="next-steps"></a>Passos seguintes

Saiba como [utilizar expressões](use-expressions-in-conditions.md) em condições no modo avançado.
