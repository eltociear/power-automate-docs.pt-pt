---
title: Descrição geral das regiões do Power Automate | Microsoft Docs
description: Descrição geral com perguntas e respostas sobre as regiões no Power Automate
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/07/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a87845247f57e58edf7170dc3e8da721db7d275e
ms.sourcegitcommit: 27ee91452be26cf5c96397c39f9f5b8bede14cdb
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/08/2020
ms.locfileid: "80862521"
---
# <a name="faq-for-regions-in-power-automate"></a>FAQ sobre s regiões no Power Automate

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

## <a name="what-features-are-specific-to-a-given-region"></a>Quais são as funcionalidades específicas de uma determinada região?

Os ambientes podem ser criados em regiões diferentes e estão vinculados a essa localização geográfica. Quando cria um fluxo num ambiente, esse fluxo é implementado em datacenters nessa localização geográfica. Isto aplica-se a todos os itens que criar nesse ambiente, incluindo o Common Data Model, fluxos, ligações, gateways, aplicações e conectores personalizados.

Para um desempenho ideal, crie o seu ambiente na região que esteja mais próxima dos seus utilizadores. Por exemplo, se os seus utilizadores estiverem na Europa, crie os ambientes na região da Europa. Se os seus utilizadores estiverem nos Estados Unidos, crie os ambientes na região dos E.U.A.

## <a name="region-mappings-for-power-automate-and-gateways"></a>Mapeamentos de regiões do Power Automate e dos gateways

A região onde o gateway está instalado tem de mapear à sua região do Power Automate. Não são suportados limites entre diferentes áreas geográficas. 

Seguem-se as informações de mapeamento:

Região do Power Platform|Região de gateway
-----|-----
Estados Unidos, incluindo pré-visualização|E.U.A. Central, E.U.A. Leste 2, E.U.A. Leste, E.U.A Centro-Norte, E.U.A. Centro-Sul, E.U.A. Oeste 2, E.U.A. Centro-Oeste, E.U.A. Oeste
Ásia|Ásia Leste, Ásia Sudeste
Austrália|Leste da Austrália, Sudeste da Austrália
Canadá|Canadá Central, Leste do Canadá
Europa|Europa do Norte, Europa Ocidental
França|França Central, Sul de França
Índia|Índia Central, Sul da Índia, Oeste da Índia
Japão|Leste do Japão, Oeste do Japão
América do Sul|Sul do Brasil
Reino Unido|Sul do Reino Unido, Oeste do Reino Unido

## <a name="is-power-automate-available-in-national-clouds"></a>O Power Automate está disponível nas clouds nacionais?
Yes. [Saiba mais](./us-govt.md).

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Que endereços IP de saída são utilizados em cada região?
Veja o artigo [Limites e configuração](limits-and-config.md).

