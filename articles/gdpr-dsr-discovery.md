---
title: Deteção de Pedidos de Titulares de Dados do RGPD no Power Automate | Microsoft Docs
description: Saiba como utilizar o Power Automate para responder a Pedidos de Deteção de Titulares de Dados do RGPD.
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
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 26bed9ab3329bbf0edf8ea055de71b732d7d0746
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74355409"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-power-automate"></a>Responder a Pedidos de Deteção de Titulares de Dados do RGPD no Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

O primeiro passo para responder a um DSR é localizar os dados pessoais objeto do pedido. Este primeiro passo ajuda-o a determinar se um DSR cumpre os requisitos da sua organização para respeitar ou recusar um pedido de DSR. Por exemplo, após localizar e analisar os dados pessoais em causa, pode determinar que o pedido não cumpre os requisitos da sua organização, uma vez que pode afetar negativamente os direitos e as liberdades de terceiros.

Segue-se um resumo dos tipos de recursos do Power Automate com dados pessoais de um utilizador específico.

|**Recursos com dados pessoais**|**Finalidade**|
|-----|-----|
|Registos gerados pelo sistema|Telemetria que captura o histórico e os eventos do sistema.|
|Histórico de execuções|O histórico de cada execução de fluxo nos últimos 28 dias. Estes dados incluem a hora de início, a hora de fim, o estado e todas as informações de entrada/saída do fluxo. [Saiba mais](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Feed de atividades| Fornece um resumo das atividades dos fluxos, incluindo o estado da execução, as falhas e as notificações.|
|Tarefas do utilizador|Não visíveis para o utilizador, as tarefas de sistema que são executadas em nome de um utilizador para a execução dos fluxos.|
|Fluxos|A lógica do fluxo de trabalho que existe para um fluxo. [Saiba mais](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Permissões dos fluxos|Os fluxos podem ser partilhados e reatribuídos a outros utilizadores. As listas de permissões existem para todos os fluxos. [Saiba mais](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Detalhes do utilizador|Detalhes, não visíveis para o utilizador, que suportam a execução dos fluxos.|
|Ligações|Utilizadas por conectores para permitir a conectividade a APIs, sistemas, bases de dados, etc. [Saiba mais](https://docs.microsoft.com/flow/add-manage-connections)|
|Permissões da ligação|Permissões para uma ligação específica. [Saiba mais](https://docs.microsoft.com/flow/add-manage-connections)|
|Conectores personalizados|Conectores personalizados criados e publicados por um utilizador para permitir a conectividade a sistemas personalizados ou de terceiros. [Saiba mais](https://docs.microsoft.com/connectors/custom-connectors/)|
|Permissões dos conectores personalizados|Listas de permissões dos conectores personalizados. [Saiba mais](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Gateway|Os gateways são serviços de dados no local que podem ser instalados por um utilizador para transferir dados de forma rápida e segura entre o Power Automate e uma origem de dados que não esteja na nuvem. [Saiba mais](https://docs.microsoft.com/flow/gateway-manage)|
|Permissões dos gateways|Os gateways podem ser partilhados com os utilizadores numa organização. [Saiba mais](https://go.microsoft.com/fwlink/?linkid=872249)|
