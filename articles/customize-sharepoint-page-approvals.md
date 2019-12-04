---
title: Gerir aprovações de páginas do SharePoint com o Power Automate | Microsoft Docs
description: Saiba como gerir aprovações de páginas do SharePoint com o Power Automate.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 9a7e6b28f7080ea65141d9a68881a637cd68cb2d
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74362723"
---
# <a name="manage-sharepoint-page-approvals-with-power-automate"></a>Gerir aprovações de páginas do SharePoint com o Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Os administradores de sites do SharePoint podem utilizar o Power Automate para pedir a aprovação de páginas novas ou atualizadas antes de serem publicadas.

Neste artigo, vai aprender a configurar o site do SharePoint de forma a este utilizar um fluxo que exige a aprovação das alterações ao site antes de se propagarem.

## <a name="configure-sharepoint-for-page-approvals"></a>Configurar o SharePoint para aprovações de páginas

### <a name="prerequisites"></a>Pré-requisitos 

Tem de ser um administrador de sites do SharePoint para executar as atividades indicadas neste artigo.

1. Inicie sessão no SharePoint como administrador de sites.
1. Selecione **Páginas** na barra de navegação.

    ![Selecionar o fluxo de aprovação de páginas](media/customize-sharepoint-page-approvals/pages.png)

1. Selecione **Fluxo** e, em seguida, selecione **Configurar o fluxo de aprovação de páginas**.
    
    ![Selecionar o fluxo de aprovação de páginas](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Introduza um **Nome do fluxo**, pelo menos um nome na caixa **Aprovadores** e, em seguida, selecione **Criar**.
    
    ![Selecionar o fluxo de aprovação de páginas](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

Já está. Agora, sempre que uma página for adicionada ou modificada, é enviado um pedido de aprovação aos **Aprovadores** indicados no fluxo.

O fluxo de aprovação de páginas é como qualquer outro fluxo e por isso é apresentado no separador **Os meus fluxos**.

![Selecionar o fluxo de aprovação de páginas](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Submeter uma página para aprovação

Agora que criou um fluxo de aprovação de páginas, qualquer pessoa que adicionar ou alterar uma página terá de fazer o seguinte:

 - Fazer uma alteração ao site (adicionar uma nova página, por exemplo) e, em seguida, guardar a alteração.

     ![Submeter página para aprovação](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Aguardar que alguém aprove a alteração.
    
    ![Submeter página para aprovação](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Aprovar uma página

Os aprovadores recebem um e-mail sempre que houver um pedido de aprovação de páginas. Podem aprovar os pedidos diretamente no e-mail (se o cliente de e-mail suportar mensagens com ações) ou abrir a página a partir do e-mail para a rever e, em seguida, aprovar a página no SharePoint.

## <a name="customize-page-approval-flows"></a>Personalizar fluxos de aprovação de páginas

Como as aprovações de páginas utilizam o Power Automate em segundo plano, o fluxo de aprovação de páginas está disponível para os proprietários de sites modificarem e adicionarem qualquer lógica de negócio personalizada ao fluxo. Para modificar o fluxo, o proprietário do site pode selecionar **Fluxos** e, em seguida, selecionar **Ver os fluxos** na biblioteca de páginas para encontrar o fluxo de aprovação de páginas.

## <a name="learn-more"></a>Saiba mais

- [Fluxo de aprovação de páginas](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Configurar a aprovação de páginas](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
