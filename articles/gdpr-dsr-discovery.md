---
title: Pedidos de Deteção dos Titulares dos Dados RGPD do Power Automate | Microsoft Docs
description: Saiba como utilizar o Power Automate para responder a Pedidos de Deteção dos Titulares dos Dados RGPD.
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
ms.openlocfilehash: 05def202f2a0b0db8a6eebb067406c96221e7d1c
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297170"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-power-automate"></a>Responder aos Pedidos de Deteção dos Titulares de Dados RGPD para o Power Automate


O primeiro passo para responder a um DSR é localizar os dados pessoais objeto do pedido. Este primeiro passo ajuda-o a determinar se um DSR cumpre os requisitos da sua organização para respeitar ou recusar um pedido de DSR. Por exemplo, após localizar e analisar os dados pessoais em causa, pode determinar que o pedido não cumpre os requisitos da sua organização, uma vez que pode afetar negativamente os direitos e as liberdades de terceiros.

Abaixo encontra-se um resumo dos tipos de recursos do Power Automate que contêm dados pessoais para um utilizador específico.

|**Recursos com dados pessoais**|**Objetivo**|
|-----|-----|
|Registos gerados pelo sistema|Telemetria que captura o histórico e os eventos do sistema.|
|Histórico de execuções|O histórico de cada execução de fluxo nos últimos 28 dias. Estes dados incluem a hora de início, a hora de fim, o estado e todas as informações de entrada/saída do fluxo. [Mais informações](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Feed de atividades| Fornece um resumo das atividades dos fluxos, incluindo o estado da execução, as falhas e as notificações.|
|Tarefas do utilizador|Não visíveis para o utilizador, as tarefas de sistema que são executadas em nome de um utilizador para a execução dos fluxos.|
|Fluxos|A lógica do fluxo de trabalho que existe para um fluxo. [Mais informações](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Permissões dos fluxos|Os fluxos podem ser partilhados e reatribuídos a outros utilizadores. As listas de permissões existem para todos os fluxos. [Mais informações](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Detalhes do utilizador|Detalhes, não visíveis para o utilizador, que suportam a execução dos fluxos.|
|Ligações|Utilizada pelos conectores, permite a conectividade a APIs, sistemas, bases de dados, etc. [Mais informações](https://docs.microsoft.com/flow/add-manage-connections)|
|Permissões da ligação|Permissões para uma ligação específica. [Mais informações](https://docs.microsoft.com/flow/add-manage-connections)|
|Conectores personalizados|Conectores personalizados criados e publicados por um utilizador para permitir a conectividade a sistemas personalizados ou de terceiros. [Mais informações](https://docs.microsoft.com/connectors/custom-connectors/)|
|Permissões dos conectores personalizados|Listas de permissões dos conectores personalizados. [Mais informações](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Gateway|Gateways são os serviços de dados no local que podem ser instalados por um utilizador para transferir dados de forma rápida e segura entre o Power Automate e uma origem de dados que não esteja na nuvem. [Mais informações](https://docs.microsoft.com/flow/gateway-manage)|
|Permissões de gateway|Os gateways podem ser partilhados com os utilizadores numa organização. [Mais informações](https://go.microsoft.com/fwlink/?linkid=872249)|
