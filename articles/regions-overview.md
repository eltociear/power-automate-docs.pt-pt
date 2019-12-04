---
title: Descrição geral das regiões do Power Automate | Microsoft Docs
description: Descrição geral com perguntas e respostas sobre as regiões no Power Automate
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
ms.date: 08/28/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0238905fe079bb0511c032fee0a3822b3c6d65c5
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74374269"
---
# <a name="faq-for-regions-in-power-automate"></a>FAQ sobre s regiões no Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Este documento fornece uma lista de perguntas mais frequentes sobre o Power Automate.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>Como sei onde está implementado o meu fluxo?
O seu fluxo está implementado na [região](https://azure.microsoft.com/regions/) que aloja o [ambiente](environments-overview-admin.md). Por exemplo, se o seu ambiente for criado na região Europa, o seu fluxo está implementado nos datacenters da Europa.

Para identificar a região, os administradores podem iniciar sessão no [centro de administração](https://admin.flow.microsoft.com) do Power Automate. O separador **Ambientes** lista todos os ambientes existentes e as respetivas regiões.

![ver ambientes](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>Que regiões estão disponíveis?
* Estados Unidos
* Europa
* Ásia
* Austrália
* Índia
* Japão
* Canadá
* América do Sul
* Reino Unido
* Governo dos E.U.A. (GCC)
* França

## <a name="what-features-are-specific-to-a-given-region"></a>Que funcionalidades são específicas de uma determinada região?
Os ambientes podem ser criados em regiões diferentes e estão vinculados a essa localização geográfica. Quando cria um fluxo num ambiente, esse fluxo é implementado em datacenters nessa localização geográfica. Isto aplica-se a todos os itens que criar nesse ambiente, incluindo modelo de dados comuns, fluxos, ligações, gateways, aplicações e conectores personalizados.

Para um desempenho ideal, crie o seu ambiente na região que esteja mais próxima dos seus utilizadores. Por exemplo, se os seus utilizadores estiverem na Europa, crie os ambientes na região da Europa. Se os seus utilizadores estiverem nos Estados Unidos, crie os ambientes na região dos E.U.A.

## <a name="gateways"></a>Gateways
Os gateways são:

* Não está disponível na região da Índia.
* Suportado apenas no ambiente predefinido, não em ambientes personalizados.

## <a name="is-power-automate-available-in-national-clouds"></a>O Power Automate está disponível nas clouds nacionais?
Sim. [Saiba mais](./us-govt.md).

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Que endereços IP de saída são utilizados em cada região?
Veja o artigo [Limites e configuração](limits-and-config.md).

