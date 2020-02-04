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
ms.date: 10/17/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: aca3291bcbda1917b669107b73f84248741dee7e
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "75867816"
---
# <a name="add-a-condition-to-a-flow"></a>Adicionar uma condição a um fluxo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Especifique que um fluxo efetua uma ou mais tarefas, apenas se uma condição for verdadeira. Especifique, por exemplo, que obterá uma mensagem de e-mail apenas se um tweet que contém uma palavra-chave for reenviado pelo menos 10 vezes.

## <a name="prerequisites"></a>Pré-requisitos

* [Criar um fluxo](get-started-logic-template.md) a partir de um modelo - este tutorial [utiliza este modelo](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) como exemplo

## <a name="add-a-condition"></a>Adicionar uma condição

1. No [Power Automate](https://flow.microsoft.com), selecione **Os meus fluxos** na barra de navegação superior.

    Poderá ter de iniciar sessão, se ainda não o tiver feito.

1. Na lista de fluxos, selecione um dos fluxos que criou.

    Este tutorial utiliza um exemplo com um acionador do Twitter e uma ação do SharePoint.

1. Selecione **Editar fluxo**.

1. Por baixo da última ação, selecione **Novo passo**.

1. Selecione **Adicionar uma condição**.

    ![Botão de condição](./media/add-condition/add-condition.png)

1. No cartão **Condição**, selecione uma área vazia na caixa à esquerda.

    A lista **Conteúdo dinâmico** é aberta.

1. Selecione o parâmetro **Contagem de tweets reenviados** para adicioná-lo à caixa.

1. Na caixa ao meio do cartão **Condição**, selecione **é maior do que ou igual a**.

1. Na caixa à direita, introduza **10**.

    ![A caixa OBJECT NAME com um parâmetro nela](./media/add-condition/specify-condition.png)

1. Selecione o cabeçalho da ação que pretende utilizar dentro da condição (por exemplo, **Criar item**) e arraste-o sob o texto que indica **If yes**.

    Quando soltar o cursor, a ação move-se para essa caixa.

    ![Ação de arrastar](./media/add-condition/drag-action.png)

1. Configure a ação conforme necessário.

1. Guarde o fluxo.

## <a name="edit-in-advanced-mode"></a>Editar no modo avançado

Também pode selecionar **Editar em modo avançado** para escrever condições mais avançadas. Pode utilizar qualquer expressão da *Linguagem de definição do fluxo de trabalho* em modo avançado. Saiba mais sobre todas as [expressões](https://msdn.microsoft.com/library/azure/mt643789.aspx) disponíveis.

## <a name="next-steps"></a>Próximos passos

Saiba como [utilizar expressões](use-expressions-in-conditions.md) em condições no modo avançado.