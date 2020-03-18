---
title: Gateway de dados no local | Microsoft Docs
description: Este artigo é uma descrição geral do gateway de dados no local do Power Automate.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2a0e2d3ff9fb39019ef4b8f37a7715229844c388
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/13/2020
ms.locfileid: "79224360"
---
# <a name="what-is-an-on-premises-data-gateway"></a>O que é um gateway de dados no local?


Um gateway de dados no local atua como uma ponte para permitir a transferência de dados rápida e segura entre dados no local (dados que não estão na cloud) e vários serviços cloud da Microsoft. Estes serviços cloud incluem o Power BI, Power Apps, Power Automate, Azure Analysis Services e Azure Logic Apps. Através da utilização de um gateway, as organizações conseguem manter bases de dados e outras origens de dados nas redes no local e, ainda assim, utilizar esses dados no local de forma segura em serviços cloud.

## <a name="how-the-gateway-works"></a>Como funciona o gateway

![Descrição geral do gateway](media/gateway-reference/on-premises-data-gateway.png)

Para obter informações acerca da forma como o gateway funciona, veja [Arquitetura do gateway de dados no local](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="types-of-gateways"></a>Tipos de gateways

Existem dois tipos diferentes de gateway, cada um para um cenário diferente:

- O **gateway de dados no local** permite que múltiplos utilizadores se liguem a múltiplas origens de dados no local. Pode utilizar um gateway de dados no local com todos os serviços suportados através de uma única instalação de gateway. Este gateway é adequado para cenários complexos com várias pessoas a acederem às várias origens de dados.

- O **gateway de dados no local (modo pessoal)** permite que um utilizador se ligue a origens e não pode ser partilhado com outras pessoas. O gateway de dados no local (modo pessoal) só pode ser utilizado com o Power BI. Este gateway é adequado para cenários em que o utilizador é a única pessoa responsável pela criação de relatórios e não precisa de partilhar nenhuma origem de dados com outras pessoas.

## <a name="use-a-gateway"></a>Utilizar um gateway

Existem quatro passos principais para utilizar um gateway.

1. [Transferir e instalar o gateway](/data-integration/gateway/service-gateway-install) num computador local.
2. [Configurar](/data-integration/gateway/service-gateway-app) o gateway com base na firewall e noutros requisitos de rede.
3. [Adicionar administradores de gateway](/data-integration/gateway/service-gateway-manage) que também consigam gerir e administrar outros requisitos de rede.
4. [Resolver problemas](/data-integration/gateway/service-gateway-tshoot) relacionados com o gateway em caso de erros.

## <a name="next-steps"></a>Próximos passos

- [Instalar o gateway de dados no local](/data-integration/gateway/service-gateway-install)
