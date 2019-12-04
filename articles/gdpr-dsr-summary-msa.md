---
title: Resumo de Pedidos de Titulares de Dados RGPD para Contas Microsoft (MSA) | Microsoft Docs
description: Saiba como responder a Pedidos dos Titulares de Dados do RGPD no Power Automate.
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
ms.openlocfilehash: 81b486c0d9ed059cc310f1297e27b28206776f45
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74367553"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>Responder a Pedidos de Direitos de Titulares de Dados (DSRs) RGPD
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este artigo descreve o Regulamento Geral Sobre a Proteção de Dados (RGPD) da União Europeia e fornece passos que pode seguir para suportar a conformidade com o RGPD para utilizadores do Power Automate que efetuam autenticação com Contas Microsoft (MSA).

## <a name="prerequisites"></a>Pré-requisitos

Necessita de uma MSA com uma [licença gratuita do Power Automate ](https://flow.microsoft.com/pricing/) para executar os passos descritos neste artigo.

>[!TIP]
> As informações de conformidade com o RGPD também estão disponíveis para utilizadores que efetuam autenticação com [contas do Azure Active Directory](gdpr-dsr-summary.md).
>
>

## <a name="respond-to-dsrs-for-power-automate-customer-data"></a>Responder a DSRs de dados de clientes do Power Automate

Um pedido formal do titular dos dados para que um responsável pelo tratamento realize uma ação nos respetivos dados pessoais denomina-se pedido de DSR (Direitos do Titular de Dados). O RGPD define dados pessoais como **quaisquer dados relacionados com uma pessoa singular identificada ou identificável**. O RGPD confere às pessoas (denominadas titulares de dados) os direitos de gerirem os dados pessoais recolhidos por um empregador, agência ou organização (denominados como o responsável pelo tratamento dos dados ou o responsável pelo tratamento). Estes direitos incluem:

* Obter cópias dos dados pessoais.
* Pedir correções aos dados pessoais.
* Restringir o processamento dos dados pessoais.
* Eliminar dados pessoais.
* Receber dados pessoais num formato eletrónico, para que possam ser transferidos para outro responsável pelo tratamento.

A Microsoft fornece produtos, serviços e ferramentas para ajudar os responsáveis pelo tratamento a localizarem e a realizarem ações nos dados pessoais em resposta a pedidos de DSR para dados alojados na cloud.

Veja a seguir uma descrição geral dos processos descritos neste guia:

1. **Deteção**: utilize as ferramentas de pesquisa e deteção para localizar facilmente os dados de clientes que podem ser objeto de um pedido de DSR. Se determinar que os documentos que recolhe cumprem as diretrizes do seu responsável pelo tratamento para realizar ações, pode realizar uma ou mais das ações de DSR descritas nos seguintes passos. Saiba mais na [Documentação de Deteção de DSR do Power Automate para Contas Microsoft](gdpr-dsr-discovery-msa.md). Em alternativa, pode determinar que o pedido não cumpre as diretrizes do seu responsável pelo tratamento para responder a pedidos de DSR.

1. **Acesso**: obtenha os dados pessoais que residem na cloud da Microsoft e, se solicitado, faça uma cópia deles para que possam estar disponíveis para o titular dos dados.

1. **Correção**: faça alterações ou implemente outras ações solicitadas nos dados pessoais, se aplicável.

1. **Restrição**: restrinja o processamento dos dados pessoais ao remover licenças para vários serviços online ou ao desativar os serviços pretendidos sempre que possível. Pode também eliminar os dados da cloud da Microsoft e retê-los no local ou noutra localização.

1. **Eliminação**: elimine permanentemente os dados pessoais que residem na cloud da Microsoft. Saiba mais sobre como [eliminar dados pessoais para Contas Microsoft](gdpr-dsr-delete-msa.md). Saiba mais sobre como [fechar uma Conta Microsoft](gdpr-dsr-accountclose-msa.md).

1. **Exportação**: forneça uma cópia eletrónica (num formato legível por computador) dos dados pessoais. [Saiba mais sobre como exportar dados pessoais para Contas Microsoft](gdpr-dsr-export-msa.md).
