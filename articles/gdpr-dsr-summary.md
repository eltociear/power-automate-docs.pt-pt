---
title: Resumo dos Pedidos dos Titulares dos Dados GDPR | Microsoft Docs
description: Saiba como responder a Pedidos de Titulares de Dados do RGPD no Power Automate.
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
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 256e874e2b70844219cd1c21e2ed37f2a96ba78c
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74367392"
---
# <a name="responding-to-gdpr-data-subject-requests-for-power-automate"></a>Responder a Pedidos de Titulares de Dados do RGPD no Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este artigo prepara-o a si e à sua organização para o Regulamento Geral sobre a Proteção de Dados (GDPR) da União Europeia. Este artigo descreve o que a Microsoft está a fazer para se preparar para o RGPD juntamente com exemplos de passos que pode seguir para suportar a conformidade com o RGPD quando utilizar o Power Apps, o Power Automate e o Common Data Service.

## <a name="prerequisites"></a>Pré-requisitos

Os utilizadores e os administradores podem realizar as ações descritas neste artigo.

### <a name="users"></a>Utilizadores

Um utilizador tem de ter uma conta ativa do Azure Active Directory com uma [licença do Power Automate](https://preview.flow.microsoft.com/pricing/). Os utilizadores que não cumpram este requisito devem solicitar a um administrador a realização destas ações.

### <a name="administrators"></a>Administradores

Poderá realizar as operações que exigem privilégios de administrador, descritos neste artigo, se iniciar sessão no [Centro de administração do Power Automate](https://admin.flow.microsoft.com/) ou no [PowerShell para Administradores do Power Apps](https://go.microsoft.com/fwlink/?linkid=871804) com uma conta que tenha estas duas permissões:

- Uma licença de avaliação ou uma licença paga do Plano 2 do Power Apps.

    [Uma licença de avaliação](http://make.powerapps.com/trial) que expira dentro de 30 dias.

- [Administrador Global do Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) ou [Administrador Global do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>Inquilinos Não Geridos
Mesmo que seja membro de um [inquilino não gerido](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover), o que significa que o inquilino do Azure AD não tem um administrador global, pode seguir os passos descritos neste artigo para exportar e remover os seus próprios dados pessoais. 

## <a name="responding-to-dsrs-for-power-automate-customer-data"></a>Resposta a DSRs de dados de clientes do Power Automate

O GDPR confere às pessoas (denominadas no GDPR como titulares dos dados) os direitos de gerirem os dados pessoais que foram recolhidos por um empregador ou outro tipo de agência ou organização (denominados como o responsável pelo tratamento dos dados ou apenas responsável pelo tratamento). Os dados pessoais são definidos de forma bastante abrangente no GDPR como quaisquer dados relacionados com uma pessoa singular identificada ou identificável. O GDPR confere direitos específicos aos titulares sobre os seus dados pessoais; estes direitos incluem obter cópias dos dados pessoais, solicitar correções aos mesmos, restringir o processamento dos dados, eliminá-los ou recebê-los em formato eletrónico para que possam ser movidos para outro responsável pelo tratamento. Um pedido formal por parte do titular dos dados para que um responsável pelo tratamento realize uma ação nos respetivos dados pessoais denomina-se um DSR (Pedido do Requerente de Dados).

Este artigo descreve como utilizar os produtos, os serviços e as ferramentas administrativas da Microsoft de modo a ajudar os responsáveis pelo tratamento a localizarem e a realizarem ações nos dados pessoais em resposta a DSRs. Especificamente, este artigo inclui como localizar, aceder e realizar ações nos dados pessoais que residem na cloud da Microsoft. Veja a seguir uma rápida descrição geral dos processos descritos neste guia:

1. Deteção: utilize as ferramentas de pesquisa e deteção para localizar mais facilmente os dados de clientes que podem ser objeto de um DSR. Após recolher os documentos potencialmente reativos, pode realizar uma ou mais das ações DSR descritas nos passos seguintes para responder ao pedido. Em alternativa, pode determinar que o pedido não cumpre as diretrizes da sua organização para responder a DSRs. [Documentação de Deteção de DSR do Power Automate](gdpr-dsr-discovery.md)

1. Acesso: obtenha os dados pessoais que residem na cloud da Microsoft e, se solicitado, faça uma cópia deles que possa estar disponível para o titular dos dados.

1. Correção: efetue alterações ou implemente outras ações solicitadas nos dados pessoais, se aplicável.

    Caso um titular dos dados solicite a correção dos dados pessoais que residem na sua organização, deve determinar, em conjunto com a sua organização, se é adequado respeitar o pedido.  A retificação dos dados pode incluir a realização de ações tais como a edição, a redação ou a eliminação dos dados pessoais.

    Pode utilizar o Azure Active Directory para gerir as identidades dos utilizadores do Power Automate. Os clientes empresariais podem gerir os pedidos de retificação de DSR, incluindo funcionalidades de edição limitadas, de acordo com a natureza de um determinado serviço Microsoft.  Na qualidade de responsável pelo tratamento de dados, a Microsoft não permite corrigir os registos gerados pelo sistema, uma vez que esses registos refletem atividades factuais e constituem um registo histórico de eventos nos serviços Microsoft.  [Mais informações sobre o DSR.](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure)

1. Restrição: restrinja o processamento dos dados pessoais ao remover licenças para vários serviços online ou ao desativar os serviços pretendidos sempre que possível. Pode também eliminar os dados da cloud da Microsoft e retê-los no local ou noutra localização.

    Os titulares dos dados podem solicitar a restrição do processamento dos seus dados pessoais.  A Microsoft fornece interfaces de programação de aplicações (APIs) e interfaces de utilizador (UIs) para este efeito.  Estas interfaces permitem ao administrador de inquilinos do cliente empresarial gerir tais DSRs através de uma combinação de exportação dos dados e eliminação dos dados. Um cliente pode (1) exportar uma cópia eletrónica dos dados pessoais do utilizador (incluindo as contas, os registos gerados pelo sistema e os registos associados) e, em seguida, (2) eliminar a conta e os dados associados que residem nos sistemas Microsoft.

1. Eliminação: elimine permanentemente os dados pessoais que residem na cloud da Microsoft. [Saiba mais sobre a eliminação de dados pessoais](gdpr-dsr-delete.md).

1. Exportação: forneça uma cópia eletrónica (num formato legível por computador) dos dados pessoais ao titular dos dados. Cada secção deste artigo descreve os procedimentos técnicos que uma organização responsável pelo tratamento de dados pode efetuar para responder a um DSR relativo aos dados pessoais na cloud da Microsoft. [Saiba mais sobre a exportação de dados pessoais](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Registos gerados pelo sistema

Veja este [guia](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) para obter mais informações sobre os registos gerados pelo sistema do Power Automate.
