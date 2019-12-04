---
title: Criar um fluxo de trabalho de aprovação paralelo e moderno | Microsoft Docs
description: Criar um fluxo de trabalho de aprovação paralela e moderna
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
ms.date: 05/09/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 223ca24325ee9aed2476d1da6ad9e986c09306d7
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74375603"
---
# <a name="create-parallel-approval-workflows-with-power-automate"></a>Criar fluxos de trabalho de aprovação paralela com o Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Num fluxo de trabalho de aprovação paralela, são necessárias múltiplas pessoas para aprovar itens, como faturas, ordens de compra, pedidos de férias, etc. A aprovação de cada pessoa é independente da aprovação de todos os outros aprovadores.

Nestas instruções, utilizamos o Power Automate para criar um fluxo que automatiza um fluxo de trabalho de aprovação paralela. Este fluxo automatiza o processo de pedido de férias de um funcionário, que requer a aprovação de todas as pessoas (ou equipas) que o funcionário ajuda regularmente. Os funcionários utilizam uma [lista do SharePoint](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) para pedir férias. São necessárias aprovações de férias do gestor direto do funcionário, da equipa de Vendas e da equipa de Recursos Humanos. Cada pedido de férias é encaminhado para cada aprovador tendo em vista uma decisão. O fluxo envia um e-mail com as alterações de estado e, em seguida, atualiza o SharePoint com as decisões.

## <a name="prerequisites"></a>Pré-requisitos

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

A lista do SharePoint Online que criar tem de incluir as seguintes colunas:

   ![Colunas de listas do SharePoint](./media/parallel-modern-approvals/sharepoint-columns.png)

Anote o nome e o URL da lista do SharePoint Online. Iremos utilizar estes itens mais tarde para configurar o acionador **SharePoint – Quando um novo item é criado**.

## <a name="create-your-flow-from-the-blank-template"></a>Criar o fluxo a partir do modelo em branco

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Adicionar um acionador

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![Informações do SharePoint](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Obter o gestor da pessoa que criou o pedido de férias

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>Dar um nome ao fluxo e guardá-lo

1. Dê um nome ao seu fluxo e, em seguida, selecione o ícone **Guardar** para guardar o trabalho feito até agora.

   ![guardar fluxo](./media/parallel-modern-approvals/save.png)

> [!NOTE]
> Selecione o ícone **Guardar** periodicamente para guardar as alterações feitas ao seu fluxo.
> 
> 


## <a name="add-an-approval-action-for-immediate-manager"></a>Adicionar uma ação de aprovação para o gestor imediato

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!IMPORTANT]
> Esta ação envia o pedido de férias para o endereço de e-mail na caixa **Atribuído A**; por conseguinte, insira o token **E-mail** da lista **Obter gestor (v2)**.
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>Inserir uma ação de aprovação de ramo paralelo para a equipa de vendas

1. Selecione a seta para baixo que está localizada entre o cartão **Obter gestor (v2)** e o cartão **Iniciar uma aprovação**.
2. Selecione o sinal de adição que aparece na seta para baixo depois de a selecionar.
3. Selecione **Adicionar um ramo paralelo**.
4. Selecionar **Adicionar uma ação**.

    ![configuração de obter gestor](./media/parallel-modern-approvals/add-parallel-branch.png)
5. Pesquise, selecione e, em seguida, configure uma ação **Iniciar uma aprovação**, que envia o pedido de férias à equipa de vendas. Veja os [passos utilizados para Adicionar uma ação de aprovação para o gestor imediato](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager), se não tiver a certeza como adicionar a ação **Iniciar uma aprovação**.

> [!IMPORTANT]
> Utilize o endereço de e-mail da equipa de vendas na caixa **Atribuído a** da ação **Iniciar uma aprovação 2**.
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>Inserir uma ação de aprovação de ramo paralelo para a equipa de recursos humanos

1. Repita os passos para [inserir um ramo paralelo para a equipe de vendas](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) para adicionar e, em seguida, configure uma ação **Iniciar uma aprovação** ação para enviar os pedidos de férias para os recursos humanos.

> [!IMPORTANT]
> Utilize o endereço de e-mail da equipa de recursos humanos na caixa **Atribuído a** da ação **Iniciar uma aprovação 3**.
> 
> 

Se seguiu todos os passos até agora, o fluxo deverá assemelhar-se a este exemplo:

   ![fluxo com ramos paralelos](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>Opções depois de adicionar ramos paralelos

Depois de adicionar ações a ramos paralelos, tem duas opções para adicionar mais passos ao fluxo:

1. Utilize o botão pequeno **Inserir um novo passo** (o botão de adição circular que é apresentado ao selecionar qualquer espaço em branco num ramo ou na área imediatamente abaixo de um ramo). Este botão adiciona um passo a esse **ramo específico**. Os passos que adicionar com este botão são executados após a conclusão deste ramo específico.
1. Utilize o botão maior **Novo passo** na parte inferior do fluxo de trabalho completo. Os passos que adicionar com este botão são executados após a conclusão de todos os ramos.

Nas secções seguintes, utilizamos o pequeno botão **Inserir um novo passo** para executar os seguintes passos em cada ramo:

* Adicionar uma condição que verifica se o pedido de férias foi aprovado ou rejeitado.
* Enviar um e-mail que informa o funcionário da decisão.
* Atualizar o pedido de férias no SharePoint com a decisão de aprovação.

Em seguida, utilizamos o botão maior **Novo passo** para enviar um e-mail que resume todas as decisões tomadas sobre o pedido de férias.

Vamos continuar:

## <a name="add-a-condition-to-each-branch"></a>Adicionar uma condição a cada ramo

1. Selecione qualquer espaço em branco no ramo **Iniciar uma aprovação**.
2. Selecione o botão pequeno **Inserir um novo passo** (o botão de adição circular que é apresentado depois de selecionar o espaço em branco no passo anterior).
3. Selecione **Adicionar uma condição** no menu que é apresentado.
4. Selecione a primeira caixa no cartão **Condição** e, em seguida, selecione o token **Resposta** na categoria **Iniciar uma aprovação** da lista de conteúdo dinâmico.

    ![fluxo com condição de ramos paralelos](./media/parallel-modern-approvals/configure-approval-condition.png)
5. Certifique-se de que a lista (no meio do **cartão Condição**) está definida como **é igual a**.
6. Introduza **Aprovar** (este texto é sensível às maiúsculas de minúsculas) na última caixa.
7. O cartão condição deve, agora, assemelhar-se a este exemplo:

    ![fluxo com condição de ramos paralelos](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > Esta condição verifica a resposta da ação **Iniciar uma aprovação** que é enviada ao gestor do funcionário.
   > 
   > 
8. Repita os passos anteriores nos ramos **Iniciar uma aprovação 2** (o pedido de aprovação para as vendas) e **Iniciar uma aprovação 3** (o pedido de aprovação para os recursos humanos).

## <a name="add-email-actions-to-each-branch"></a>Adicionar ações de e-mail a cada ramo

Execute os seguintes passos no lado **SE SIM** do ramo **Condição**.

   Nota: o fluxo utiliza estes passos para enviar um e-mail quando o pedido for aprovado:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar o modelo de e-mail pré-aprovado](includes/media/parallel-modern-approvals/yes-email-config.png)

Para enviar um e-mail quando um pedido é rejeitado, utilize o lado **SE NÃO** do ramo **Condição** e, em seguida, repita os passos anteriores para adicionar um modelo para o e-mail de rejeição.

Repita os passos anteriores nos ramos **Iniciar uma aprovação 2** (o pedido de aprovação para as vendas) e **Iniciar uma aprovação 3** (o pedido de aprovação para os recursos humanos).

## <a name="update-the-vacation-request-with-the-decision"></a>Atualizar o pedido de férias com a decisão

Execute os seguintes passos para atualizar o SharePoint ao tomar decisões.

   Nota: certifique-se de que executa estes passos nos lados **SE SIM** e **SE NÃO** do ramo.

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![configuração da atualização do item](./media/parallel-modern-approvals/configure-update-item.png)

Repita os passos anteriores nos ramos **Iniciar uma aprovação 2** e **Iniciar uma aprovação 3**.

## <a name="complete-the-flow"></a>Concluir o fluxo

1. Selecione **Novo passo** > **Adicionar uma ação**

    ![configuração da atualização do item](includes/media/parallel-modern-approvals/add-an-action-2-step.png)
1. Utilize os passos fornecidos anteriormente para enviar um e-mail que resume os resultados de cada aprovação. Envie este e-mail para o funcionário que pediu as férias. O cartão poderá assemelhar-se a este exemplo:

   ![configuração da atualização do item](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>Saiba mais sobre as aprovações modernas

[Introdução às aprovações modernas](modern-approvals.md)

