---
title: Saiba como gerir gateways de dados no local | Microsoft Docs
description: Ver e instalar um gateway de dados no local no Power Automate.
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
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 019d711771c10f360b1f5c7dab61aa432c827311
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74367116"
---
# <a name="manage-an-on-premises-data-gateway-in-power-automate"></a>Gerir um gateway de dados no local no Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Instale e faça a gestão de um gateway de dados no local para integrar, de forma segura, uma variedade de aplicações baseadas na cloud com os dados e aplicações no local através do Power Automate.

Com um gateway, pode ligar aos dados no local através destas ligações:

* Apache Impala
* Conectores personalizados que criou
* DB2
* Sistema de Ficheiros
* HTTP com o Azure AD
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata (Pré-visualização)

> [!IMPORTANT]
> Os gateways de dados do Microsoft SharePoint suportam agora o tráfego HTTP e HTTPS.

## <a name="prerequisites"></a>Pré-requisitos

* O nome de utilizador e palavra-passe que utilizou para [se inscrever](sign-up-sign-in.md) no Power Automate.
* Permissões administrativas num gateway.

  Tem estas permissões por predefinição para cada gateway que instalar. Além disso, um administrador de outro gateway pode conceder-lhe estas permissões para esse gateway.
* Uma licença que suporta gateways. Para mais informações, consulte a secção "Connectivity (Conectividade)" da [pricing page (página de preços)](https://flow.microsoft.com/pricing/).

> [!NOTE]
> Só pode criar um gateway e uma ligação no local no seu [ambiente predefinido](environments-overview-maker.md).

## <a name="install-a-gateway"></a>Instalar um gateway

Para instalar um gateway, siga os passos em [Instalar um gateway de dados no local](/data-integration/gateway/service-gateway-install). Instale o gateway no modo padrão. O _gateway de dados no local (modo pessoal)_ está disponível apenas para o Power BI.

## <a name="view-your-gateways"></a>Ver os gateways

No canto superior direito do [site do Power Automate](https://flow.microsoft.com), selecione o ícone de engrenagem e, em seguida, selecione **Gateways**.

![Gateway em gestão][1]

> [!NOTE]
> Se tiver criado ou lhe tiver sido dado acesso a um gateway no Power Apps, esse gateway é apresentado na lista **Os meus gateways** no Power Automate.

## <a name="cluster-your-gateways"></a>Criar clusters dos gateways

Pode criar [clusters de instalações de gateways de dados no local de elevada disponibilidade](/data-integration/gateway/service-gateway-high-availability-clusters) para evitar pontos únicos de falha no acesso a recursos de dados no local.

Por predefinição, o Power Automate utiliza o gateway principal no cluster. Se o gateway principal não estiver disponível, o serviço muda para o gateway seguinte no cluster e assim sucessivamente.

Assim que tiver configurado um cluster de gateway, poderá permitir que o tráfego seja distribuído por todos os gateways no cluster.

Siga estes passos para distribuir o tráfego entre os gateways:

1. Selecione **Dados** na barra de navegação à esquerda.
1. Selecione **Gateways**.
1. Selecione qualquer um dos gateways.
1. Selecione **Distribuir pedidos por todos os gateways ativos neste cluster**.
1. Selecione **Aplicar** para guardar as alterações.

Para obter mais informações, veja [Compreender os gateways](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
