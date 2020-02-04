---
title: Saiba como ligar aos seus dados através de ligações e gateways de dados no local | Microsoft Docs
description: Adicione ou faça a gestão de ligações ao SharePoint, SQL Server, OneDrive para Empresas, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google Drive e muito mais
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
ms.date: 02/15/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f2e46711637497120872848f239d59651ab875d5
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74358100"
---
# <a name="manage-connections-in-power-automate"></a>Gerir ligações no Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Se criar uma ligação no Power Automate, poderá aceder facilmente aos seus dados durante a criação de fluxos. O Power Automate inclui ligações utilizadas habitualmente, incluindo SharePoint, SQL Server, Office 365, OneDrive para Empresas, Salesforce, Excel, Dropbox, Twitter e muito mais. As ligações são partilhadas com o Power Apps, para que, quando cria uma ligação num produto, a mesma apareça no outro.

Por exemplo, pode utilizar uma ligação para realizar estas tarefas:

* Atualizar uma lista do SharePoint
* Obter dados de um ficheiro do Excel a partir da sua conta do OneDrive para Empresas ou do Dropbox.
* Enviar e-mails no Office 365.
* Enviar tweets.

Pode criar ligações em vários cenários, tais como:

* Criação de um [fluxo a partir de um modelo](get-started-logic-template.md)
* Criação de um [fluxo a partir do valor em branco](get-started-logic-flow.md) ou atualizar um fluxo existente
* Criação de uma ligação diretamente no [site do Power Automate][1]

Este tópico mostra como gerir ligações no [site do Power Automate][1].

## <a name="add-a-connection"></a>Adicionar uma ligação
1. No [site do Power Automate][1], inicie sessão com a sua conta profissional ou da organização.
2. Perto do canto superior direito, selecione o ícone de engrenagem e, em seguida, selecione **Ligações**.
   
    ![Selecionar ligações](./media/add-manage-connections/connections-menu.png)
3. Selecione **Criar ligação**.
4. Na lista **Ligações disponíveis**, selecione a ligação que pretende configurar, como o SharePoint.
5. Selecione o botão **Criar ligação** e introduza as suas credenciais para configurá-la.

Quando a ligação estiver configurada, é listada em **As minhas ligações**.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Ligue-se aos dados através de um gateway de dados no local
Na data da elaboração deste documento, o SQL Server e o SharePoint Server suportam o gateway de dados no local. Para criar uma ligação que utiliza um gateway:

1. Siga os passos descritos anteriormente neste tópico para adicionar uma ligação.
2. Na lista **Ligações disponíveis**, selecione **SQL Server** e, em seguida, selecione a caixa de verificação **Ligar através do gateway de dados no local**.
   
    ![Selecionar gateway](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Os gateways de dados do Microsoft SharePoint suportam tráfego HTTP, mas não tráfego HTTPS.
   > 
   > 
3. Indique as credenciais da ligação e selecione o gateway que pretende utilizar.
   
    Para obter mais informações, veja os tópicos [Gerir gateways](gateway-manage.md) e [Compreender gateways](gateway-reference.md).
   
    Quando a ligação estiver configurada, é listada em **As minhas ligações**.

## <a name="delete-a-connection"></a>Eliminar uma ligação
1. Vá para a página **As minhas ligações** e selecione o ícone de caixote do lixo da ligação que quer eliminar.
   
    ![Eliminar a ligação](./media/add-manage-connections/delete-connection.png)
2. Selecione **OK** para confirmar que pretende eliminar a ligação.
   
    ![Confirmar a eliminação](./media/add-manage-connections/delete-confirmation.png)

Quando elimina uma ligação, esta é removida do Power Apps e do Power Automate.

## <a name="update-a-connection"></a>Atualizar uma ligação
Pode atualizar ligações que não estejam a funcionar porque os detalhes da sua conta ou a sua palavra-passe foram alterados.

1. Vá para a página **As minhas ligações** e selecione a ligação **Verificar palavra-passe** da ligação que pretende atualizar.
   
    ![Verificar a palavra-passe](./media/add-manage-connections/verify-password.png)
2. Quando lhe for pedido, atualize a ligação com novas credenciais.

Quando atualiza uma ligação, esta é atualizada no Power Apps e no Power Automate.

## <a name="troubleshoot-a-connection"></a>Resolver problemas relacionados com ligações
Dependendo das políticas da sua organização, poderá ter de utilizar a mesma conta para iniciar sessão no Power Automate e criar uma ligação para o SharePoint, o Office 365 ou o OneDrive para Empresas.

Por exemplo, poderá iniciar sessão no Power Automate com *yourname@outlook.com* , mas ser bloqueado quando tenta ligar ao SharePoint com *yourname@contoso.com* . Em alternativa, pode iniciar sessão no Power Automate com *yourname@contoso.com* e conseguirá ligar ao SharePoint.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
