---
title: Criar fluxos de aprovação com respostas personalizadas | Microsoft Docs
description: Crie fluxos de aprovação com respostas personalizadas.
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
ms.date: 05/04/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- maker
ms.openlocfilehash: dc2eaf9ac0ffc0edb10f5cb096ee98dad6aac55d
ms.sourcegitcommit: 9cca2a2fca8371ab883b12011c1c4485ceb9c761
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200508"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Criar opções de respostas personalizadas para fluxos de aprovação


Vamos supor que quer enviar um pedido de aprovação sempre que um funcionário carregar um relatório de despesas para o SharePoint e, em seguida, permitir que o aprovador responda com uma das três opções: Aceitar, Precisa de mais informações ou Rejeitar.


## <a name="prerequisites"></a>Pré-requisitos

- Uma conta do Power Automate.
- Uma lista do SharePoint para os funcionários introduzirem os relatórios de despesas.

## <a name="create-approval-flow"></a>Criar um fluxo de aprovação
1. Iniciar sessão no [Power Automate](https://flow.microsoft.com).
1. Selecione **Os meus fluxos** na barra de navegação esquerda.
1. Selecione **Novo** > **Automatizado – do zero**.

    ![Opção Criar do zero](media/create-approval-response-options/create-approval-response-options.png)

1. No ecrã apresentado, indique um nome para o fluxo em **Nome do fluxo**. 
  
1. Procure **SharePoint** em **Escolher o seu acionador do fluxo**, selecione **Quando um item é criado** na lista de acionadores e, depois, selecione **Criar**.

   ![Selecionar Criar do zero](media/create-approval-response-options/create-from-blank.png)

1. Introduza o **Endereço do Site**  do SharePoint e o **Nome da Lista**. 

   >[!TIP]
   >Selecione **Introduzir valor personalizado** no campo **Endereço do Site** antes de introduzir texto em **Endereço do Site**.

1. Selecione **Novo passo**, procure **Aprovação** e, em seguida, selecione **Iniciar e aguardar uma aprovação**.

1. No cartão **Iniciar e aguardar uma aprovação**, selecione a lista **Tipo de aprovação**.

1. Selecione **Respostas Personalizadas – Aguardar uma resposta**.

    ![Tipo de aprovação](media/create-approval-response-options/select-approval-type.png)

    Em seguida, vai criar as respostas personalizadas que os aprovadores utilizarão quando responderem a um pedido de aprovação de despesas de um funcionário.


1. Na caixa **Opções de resposta Item**, introduza **Aceitar** e, em seguida, selecione **Adicionar novo item**. 

    ![Resposta personalizada 1](media/create-approval-response-options/enter-response-1.png)

1. Na caixa **Opções de resposta Item**, introduza **Rejeitar** e, em seguida, selecione **Adicionar novo item**.

1. Na caixa **Opções de resposta Item**, introduza **Precisa de mais informações**.

    ![Resposta personalizada 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Introduza um **Título**, **Atribuído a** (e-mail do aprovador) e os **Detalhes** (os detalhes a inserir no pedido de aprovação).

    Veja a seguir um exemplo do que pode incluir para a sua organização.

    ![Detalhes das respostas personalizadas](media/create-approval-response-options/enter-title-assigned-to-details.png)


Agora que criou as respostas personalizadas, pode querer ter ações diferentes no seu fluxo, consoante a resposta do aprovador.


## <a name="use-approval-responses"></a>Utilizar respostas de aprovação 

Se a resposta ao pedido for **Aceitar**, poderá querer enviar um e-mail para o departamento de contabilidade a pedir para reembolsar o funcionário pela despesa. 

Se a resposta for **Rejeitar**, poderá querer enviar um e-mail ao funcionário a informar que o pedido foi rejeitado.

E, finalmente, se a resposta do aprovador for **Precisa de mais informações**, poderá querer enviar um e-mail ao funcionário a solicitar mais informações.

Para dar qualquer uma destas respostas no fluxo, adicione uma ação de [**Condição**](add-condition.md) ou de **Comutador** ao fluxo e, em seguida, selecione o campo **Resultado** do pedido de aprovação no seletor de conteúdo dinâmico. Garanta que confirma se o valor é Aceitar, Precisa de mais informações ou Rejeitar.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Responder a pedidos de aprovação com uma resposta personalizada

Os aprovadores recebem pedidos de aprovação por e-mail. Os pedidos também são apresentados no centro de aprovação do Power Automate. 

![E-mail de pedido de aprovação](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Saiba mais
- Criar [fluxos de aprovador únicos](modern-approvals.md)
- Criar [fluxos de aprovador sequenciais](sequential-modern-approvals.md)
