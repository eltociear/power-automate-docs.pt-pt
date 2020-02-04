---
title: Automatize facilmente fluxos de trabalho de aprovação. | Microsoft Docs
description: Automatize fluxos de trabalho de aprovação que integram com o SharePoint, Dynamics CRM, Salesforce, OneDrive para Empresas, Zendesk ou WordPress.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c174ad7fe18539a7dc1d44acf315d569f4b35a39
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74376523"
---
# <a name="create-and-test-an-approval-workflow-with-power-automate"></a>Criar e testar um fluxo de trabalho de aprovação com o Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Com o Power Automate, pode gerir a aprovação de documentos ou processos em vários serviços, incluindo no SharePoint, Dynamics 365, Salesforce, OneDrive para Empresas, Zendesk ou WordPress.

Para criar um fluxo de trabalho de aprovação, adicione a ação **Aprovações - iniciar uma aprovação** a qualquer fluxo. Depois de adicionar esta ação, o fluxo pode gerir a aprovação de documentos ou processos. Por exemplo, pode criar fluxos de aprovação de documentos que aprovam faturas, ordens de intervenção ou cotações de vendas. Também pode criar fluxos de aprovação de processos que aprovem pedidos de férias, horas extraordinárias ou planos de viagens.

Os aprovadores podem responder a pedidos a partir da caixa de entrada do e-mail, do [centro de aprovações](https://flow.microsoft.com/manage/approvals/received/) no site do Power Automate ou da aplicação Power Automate.

## <a name="create-an-approval-flow"></a>Criar um fluxo de aprovação
Eis uma descrição geral do fluxo que iremos criar e testar:

   ![descrição geral do fluxo](./media/modern-approvals/create-flow-overview.png)

O fluxo realiza os seguintes passos:

1. Inicia quando alguém cria um pedido de férias numa lista do SharePoint Online.
2. Adiciona o pedido de férias ao centro de aprovação e, em seguida, envia por e-mail ao aprovador.
3. Envia um e-mail com a decisão da aprovação à pessoa que pediu férias.
4. Atualiza a lista do SharePoint Online com os comentários da decisão do aprovador.

## <a name="prerequisites"></a>Pré-requisitos
Para concluir estas instruções, tem de ter acesso:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Crie estas colunas na sua lista do SharePoint Online:

   ![Colunas da lista do SharePoint Online](./media/modern-approvals/sharepoint-list-fields.png)

Anote o nome e o URL da lista do SharePoint Online. Precisará destes itens mais tarde quando configurar o acionador **SharePoint – Quando um item é criado**.

## <a name="create-your-flow-from-the-blank-template"></a>Criar o fluxo a partir do modelo em branco
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Adicionar um acionador

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

O **Endereço do Site** e o **Nome da Lista** são os itens que anotou anteriormente nestas instruções.

![Informações do SharePoint](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Adicionar uma ação de perfil

1. Selecione **Novo passo** e, em seguida, selecione **Adicionar uma ação**.
   
    ![novo passo](./media/modern-approvals/select-sharepoint-add-action.png)
2. Introduza **perfil** na caixa de pesquisa **Escolher uma ação**.
   
    ![pesquisar perfil](./media/modern-approvals/search-for-profile.png)
3. Localize e, em seguida, selecione a ação **Utilizadores do Office 365 - Obter o meu perfil**.
   
    ![selecionar utilizadores do office](./media/modern-approvals/select-my-profile.png)
4. Dê um nome ao seu fluxo e, em seguida, selecione **Criar fluxo** para guardar o trabalho feito até agora.
   
    ![guardar fluxo](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>Adicionar uma ação de aprovação

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> Esta ação envia o pedido de aprovação para o endereço de e-mail na caixa **Atribuído a**.
>
> Se o cenário o exigir, poderá anexar ficheiros aos pedidos de aprovação que utilizam o Common Data Service.

## <a name="add-a-condition"></a>Adicionar uma condição

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Adicionar uma ação de e-mail para aprovações

Siga estes passos para enviar um e-mail caso o pedido de férias seja aprovado:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar modelo de e-mail de aprovação](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Adicionar uma ação de atualização para pedidos aprovados

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> Os campos **Endereço do Site**, **Nome da Lista**, **ID** e **Título** são obrigatórios.
>
>

![configuração da atualização do item](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Adicionar uma ação de e-mail para rejeições

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![configuração para pedidos rejeitados](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Adicionar a ação de atualização para pedidos rejeitados

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > Os campos **Endereço do Site**, **Nome da Lista**, **ID** e **Título** são obrigatórios.
   >
   >

![cartão atualizar item](./media/modern-approvals/configure-update-item-no.png)

1. Selecione **Atualizar fluxo** para guardar o trabalho feito até agora.
   
    ![selecionar ação de atualização](./media/modern-approvals/update.png)

Se seguiu todos os passos até agora, o fluxo deverá assemelhar-se a esta captura de ecrã:

![descrição geral do fluxo](./media/modern-approvals/completed-flow.png)

Agora que criámos o fluxo, está na altura de o testar!

## <a name="request-an-approval"></a>Pedir aprovação

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]


## <a name="create-long-running-approvals"></a>Criar aprovações de execução prolongada

Se for provável que o fluxo seja executado durante mais de 30 dias, considere armazenar as aprovações no Common Data Service. Esta opção permite-lhe criar fluxos que agem em resposta a pedidos de aprovação, mesmo após a execução do fluxo original atingir o tempo limite. Para o fazer, utilize dois fluxos, um para enviar um pedido de aprovação e o outro para executar a lógica de negócio nas respostas ao pedido de aprovação, com base na ação **Criar uma aprovação (v2)** . Saiba mais sobre as [aprovações de execução prolongada](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/long-lived-approvals-other-approval-improvements).

>[!TIP]
> Se utilizar clientes de e-mail modernos, não precisará de ficar a pensar se um pedido ainda é necessário, dado que o Power Automate atualiza automaticamente o e-mail para indicar que a aprovação está concluída.

## <a name="cancel-an-approval-requests"></a>Cancelar pedidos de aprovação

Por vezes, poderá querer cancelar um pedido de aprovação que enviou. Possivelmente, cometeu um erro no pedido ou este já não é relevante. Em qualquer um dos casos, a pessoa que enviou o pedido poderá cancelá-lo com estes passos:

1. Selecionar a aprovação.
1. Selecionar **Cancelar aprovação** no painel lateral.

>[!TIP]
>Pode sempre selecionar o separador **Histórico** para ver os pedidos de aprovação que cancelou.

>[!NOTE]
> A funcionalidade de cancelamento é suportada na ação **Criar uma aprovação (v2)** .

## <a name="request-approvals-from-guest-users"></a>Pedir aprovações a utilizadores convidados

Pode enviar pedidos de aprovações para pessoas fora da sua organização. Para o fazer, utilize os utilizadores convidados do Azure Active Directory (AAD). para tal, [convide os utilizadores de outros inquilinos como convidados](https://docs.microsoft.com/azure/active-directory/b2b/add-user-without-invite).

Quando atribui uma função a um convidado, será concedida a permissão necessária ao convidado para participar no processo de aprovação.

Agora que já criou e testou o fluxo, certifique-se de que permite que os outros utilizadores saibam como utilizá-lo.

## <a name="learn-more"></a>Saiba mais

* Ver e gerir [pedidos de aprovação pendentes](approve-reject-requests.md)
* Criar [fluxos de aprovação sequenciais.](sequential-modern-approvals.md)
* Criar [fluxos de aprovação paralelos.](parallel-modern-approvals.md)
* Instale a aplicação móvel do Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows)
