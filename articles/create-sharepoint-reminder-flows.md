---
title: Criar um fluxo de lembretes para itens do SharePoint | Microsoft Docs
description: Crie fluxos para o avisarem acerca das datas de vencimento de itens do SharePoint.
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
ms.date: 04/30/2019
ms.author: deonhe
ms.openlocfilehash: 09ee39c918bb35721ee77a7cdcd432755ccfa8c4
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74362010"
---
# <a name="sharepoint-remind-me"></a>Lembretes do SharePoint
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

As bibliotecas e listas do SharePoint permitem definir colunas de metadados personalizadas para controlar as datas. Com a integração do Power Automate no SharePoint, pode criar facilmente fluxos de lembretes com base em colunas DateTime no SharePoint. Com os fluxos de lembretes, receberá um alerta pessoal por e-mail com um número de dias predeterminado de antecedência relativamente à data de qualquer documento ou item no SharePoint.

## <a name="prerequisites"></a>Pré-requisitos
- Acesso ao Microsoft SharePoint Online.
- Uma lista ou uma biblioteca do SharePoint com uma coluna DateTime.
- Acesso ao Power Automate.

## <a name="create-a-reminder-flow"></a>Criar um fluxo de lembretes

 1. Crie uma [lista do SharePoint](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) com, pelo menos, uma coluna DateTime na vista atual. 
 1. Selecione **Fluxo** > **Definir um lembrete** > **Data desativada** (esta é a coluna com a instrução DateTime do lembrete).

     ![Selecionar o fluxo do lembrete](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. Introduza o **Nome do fluxo** e o número de dias anteriores à entrada da coluna DateTime para indicar quando quer receber o alerta do lembrete no cartão **Definir um lembrete**.

    ![Definir detalhes do fluxo de lembrete](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Selecione **Criar** no cartão **Definir um lembrete**.

1. Receberá a seguinte mensagem a indicar que o fluxo foi criado:

    ![Fluxo de lembrete criado](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Confirmar os lembretes recebidos

Receberá um lembrete por e-mail, com base na entrada **Relembrar-me vários dias antes** introduzida no fluxo **Definir um lembrete** que criou anteriormente. 

## <a name="edit-your-flow"></a>Editar o fluxo

O fluxo de lembretes é como qualquer outro fluxo e, como tal, pode aceder e editar o mesmo através do [Power Automate](https://flow.microsoft.com).

## <a name="learn-more"></a>Saiba mais

- Introdução ao [Power Automate](https://flow.microsoft.com)
- Definir um [fluxo de lembrete](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) no SharePoint.

