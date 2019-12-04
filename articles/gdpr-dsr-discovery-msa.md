---
title: Pedidos de Deteção de Titulares de Dados RGPD no Power Automate para Contas Microsoft (MSA) | Microsoft Docs
description: Saiba como utilizar o Power Automate para responder a Pedidos de Deteção de Titulares de Dados RGPD para Contas Microsoft.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/16/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 2830d08832bad330ec67717234f5a8cb0482d3a9
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74369048"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>Responder a Pedidos de Deteção de Titulares de Dados RGPD 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

O primeiro passo para responder a um pedido de DSR é localizar os dados pessoais objeto do pedido.
Segue-se um resumo dos recursos do Power Automate que contêm dados pessoais de um utilizador que efetua a autenticação com a respetiva Conta Microsoft (MSA).

|Recurso|Finalidade|
|-----|-----|
|Histórico de execuções|Fornece o histórico da execução de cada fluxo nos últimos 28 dias. Estes dados incluem a hora de início, a hora de fim, o estado e todas as informações de entrada/saída de cada execução de fluxo. Saiba mais sobre o [histórico de execuções de fluxo](https://flow.microsoft.com/blog/download-history-recurrence/).|
|Feed de atividades| Fornece um resumo das atividades de cada fluxo, incluindo o estado da execução, as falhas e as notificações.|
|Fluxos|A lógica de fluxo de trabalho para um [fluxo](https://docs.microsoft.com/flow/get-started-logic-flow).|
|Ligações|Utilizadas por conectores para permitir a conectividade a APIs, sistemas, bases de dados, etc. Saiba mais sobre [ligações](add-manage-connections.md).|

