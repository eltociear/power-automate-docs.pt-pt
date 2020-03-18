---
title: Criar um fluxo de trabalho de aprovação moderno com vários aprovadores | Microsoft Docs
description: 'Criar um fluxo de trabalho de aprovação moderna com vários aprovadores '
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 28199ab8b2a2dbf18ef89b905b2bdd362ff9e82b
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194100"
---
# <a name="manage-sequential-approvals-with-power-automate"></a>Gerir aprovações sequenciais com o Power Automate

Alguns fluxos de trabalho exigem pré-aprovação antes da aprovação do aprovador final. Por exemplo, uma empresa pode ter uma política de aprovação sequencial que requer aprovação prévia para faturas acima de $1000,00, antes de serem aprovadas pelo departamento Financeiro.

Nestas instruções, criamos um fluxo de aprovação sequencial que gere os pedidos de férias dos funcionários.

> [!NOTE]
> O SharePoint é utilizado aqui apenas como um exemplo; não é necessário para criar fluxos de aprovação. Pode utilizar qualquer um dos mais de 200 serviços com os quais o Power Automate está integrado para controlar os fluxos.


## <a name="detailed-steps-in-the-flow"></a>Passos detalhados do fluxo
O fluxo:

1. Inicia quando um funcionário cria um pedido de férias numa [lista do SharePoint Online](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7).
2. Adiciona o pedido de férias ao centro de aprovação e, em seguida, envia o pedido por e-mail ao pré-aprovador.
3. Envia a decisão de pré-aprovação por e-mail ao funcionário.
4. Atualiza a lista do SharePoint Online com a decisão e os comentários do pré-aprovador.
   
   Nota: se o pedido tiver sido pré-aprovado, o fluxo continuará com estes passos:
5. Envia o pedido para o aprovador final.
6. Envia a decisão final por e-mail ao funcionário.
7. Atualiza a lista do SharePoint com a decisão final.

Esta imagem resume os passos anteriores:

   ![diagrama visio do fluxo](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>Pré-requisitos
[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Para o efeito destas instruções, a lista do SharePoint Online que criar tem de incluir as seguintes colunas:

   ![Colunas de listas do SharePoint](./media/sequential-modern-approvals/sharepoint-columns.png)

Anote o nome e o URL da lista do SharePoint Online. Iremos utilizar estes itens mais tarde quando configurar o acionador **SharePoint - Quando um novo item é criado**.

## <a name="create-your-flow-from-the-blank-template"></a>Criar o fluxo a partir do modelo em branco
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Adicionar um acionador
[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![informações do sharepoint](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Obter o gestor da pessoa que criou o pedido de férias
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

1. Dê um nome ao seu fluxo e, em seguida, selecione **Criar fluxo** para guardar o trabalho feito até agora.
   
    ![guardar fluxo](./media/sequential-modern-approvals/save.png)
   
   > [!NOTE]
   > Selecione **Atualizar fluxo** na parte superior do ecrã periodicamente para guardar as alterações do fluxo.
   > 
   > 
   
    ![selecionar ação de atualização](./media/sequential-modern-approvals/update.png)

Depois de cada operação de guardar, selecione **Editar fluxo** na parte superior do ecrã e, em seguida, prossiga as alterações.

## <a name="add-an-approval-action-for-pre-approvals"></a>Adicionar uma ação de aprovação para pré-aprovações
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

Nota: esta ação envia o pedido de pré-aprovação para o endereço de e-mail na caixa **Atribuído A**.

## <a name="add-a-condition"></a>Adicionar uma condição
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> Esta condição verifica a resposta da ação **Iniciar uma aprovação**.
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>Adicionar uma ação de e-mail para pré-aprovações
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar o modelo de e-mail pré-aprovado](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>Adicionar uma ação de atualização para pedidos pré-aprovados
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![configuração da atualização do item](./media/sequential-modern-approvals/configure-update-item.png)

## <a name="get-the-pre-approvers-manager"></a>Obter o gestor do pré-aprovador
1. Utilize os passos para [Obter o gestor da pessoa que criou o pedido de férias](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request) que efetuamos anteriormente para adicionar e, em seguida, configure outra ação **Obter gestor**. Desta vez, vamos obter o gestor do pré-aprovador.
2. O cartão **Obter gestor 2** deve assemelhar-se a esta imagem quando tiver concluído. Certifique-se de que utiliza o token de **E-mail** da categoria **Obter gestor** no cartão **Adicionar conteúdo dinâmico a partir das aplicações e serviços utilizados neste fluxo**.
   
   ![obter o gestor do pré-aprovador](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>Adicionar a ação de aprovação final
1. Utilize os passos para [adicionar uma ação de aprovação para pré-aprovações](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals) que efetuamos anteriormente e, em seguida, configure outra ação para **Iniciar uma aprovação**. Esta ação envia uma pedido por e-mail para aprovação final.
2. Quando tiver concluído, o cartão deve assemelhar-se a esta imagem:
   
    ![configurar a aprovação](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>Adicionar a condição de aprovação final
1. Repita os passos para [adicionar uma condição](sequential-modern-approvals.md#add-a-condition) para adicionar e, em seguida, configure uma **Condição** que verifique a decisão final do aprovador.

## <a name="send-email-with-final-approval"></a>Enviar um e-mail com aprovação final
1. Utilize os passos para [Adicionar uma ação de e-mail para pré-aprovações](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) para adicionar e, em seguida, configure uma ação que envie um e-mail quando os pedidos de férias forem aprovados.
2. Quando tiver concluído, o cartão deve assemelhar-se a esta imagem:
   
   ![modelo de e-mail de aprovação final](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>Atualizar o SharePoint com a aprovação
1. Utilize os passos para [Adicionar uma ação de atualização para pedidos pré-aprovados](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) para adicionar e, em seguida, configure uma ação que atualize o SharePoint quando o pedido de férias for aprovado.
2. Quando tiver concluído, o cartão deve assemelhar-se a esta imagem:
   
    ![configuração da atualização do item](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>Enviar um e-mail com a rejeição da pré-aprovação
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![configuração para pedidos rejeitados](./media/sequential-modern-approvals/configure-rejected-email.png)

Nota: esta ação tem de ser adicionada ao ramo **SE NÃO, NÃO FAZER NADA** abaixo do cartão **Condição**.

## <a name="update-sharepoint-with-pre-approval-rejection"></a>Atualizar o SharePoint com a rejeição da pré-aprovação
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![atualizar o sharepoint relativamente a pedidos rejeitados](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>Enviar um e-mail com a rejeição final
1. Utilize os passos para [Enviar um e-mail com a rejeição da pré-aprovação](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) para adicionar e, em seguida, configure uma ação que envia um e-mail quando o pedido de férias é rejeitado pelo aprovador final.
   
    Nota: esta ação tem de ser adicionada ao ramo **SE NÃO, NÃO FAZER NADA** abaixo do cartão **Condição 2**.
2. Quando tiver concluído, o cartão deve assemelhar-se a esta imagem:
   
   ![configuração para pedidos rejeitados](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>Atualizar o SharePoint com a rejeição final
1. Utilize os passo para [Atualizar o SharePoint com a rejeição da pré-aprovação](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) para adicionar e, em seguida, configure uma ação que atualize o SharePoint se o aprovador final rejeitar o pedido de férias.
2. Quando tiver concluído, o cartão deve assemelhar-se a esta imagem:
   
   ![cartão atualizar item](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
3. Selecione **Atualizar fluxo** para guardar o trabalho feito até agora.
   
   ![selecionar ação de atualização](./media/sequential-modern-approvals/update.png)

Se seguiu todos os passos até agora, o fluxo deverá assemelhar-se a esta imagem:

![descrição geral do fluxo](./media/sequential-modern-approvals/completed-flow.png)

Agora que criamos o fluxo, vamos vê-lo em ação.

## <a name="request-an-approval"></a>Pedir aprovação
[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

O seu pedido deverá assemelhar-se a esta imagem:

![pedido de férias](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>Ver pedidos de aprovação pendentes
[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>Pré-aprovar um pedido
[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>Aprovar o pedido
Os passos para aprovar um pedido são idênticos aos passos para [pré-aprovar um pedido](sequential-modern-approvals.md#pre-approve-a-request).

Nota: o aprovador final obtém o pedido de férias apenas depois de o pedido ter sido pré-aprovado.

## <a name="reject-a-request"></a>Rejeitar um pedido
[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>Mais informações
[Instruções para aprovações modernas com um único aprovador](modern-approvals.md)

