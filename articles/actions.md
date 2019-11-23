---
title: Utilizar ações | Microsoft Docs
description: Com as Ações, pode realizar operações como Criar, Atualizar, Eliminar, Atribuir ou Efetuar Ação. Internamente, uma ação cria uma mensagem personalizada
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e3b5d53e72cff93f853bafd89f8a51200a7e735f
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74354604"
---
# <a name="use-actions"></a>Utilizar ações
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

As Ações abrem um leque de possibilidades para compor a lógica de negócio. Com as Ações, pode realizar operações como Criar, Atualizar, Eliminar, Atribuir ou Efetuar Ação. Internamente, uma ação cria uma mensagem personalizada. Os programadores designam estas ações de "mensagens". Cada uma destas mensagens baseia-se nas ações realizadas num registo de entidade. Se o objetivo de um processo for a criação de um registo e, em seguida, a atualização e a atribuição do mesmo, há três passos separados. Cada passo é definido pelas funcionalidades da entidade (e não necessariamente do seu processo de negócio).  
  
As ações permitem definir um único verbo (ou mensagem) que corresponde a uma operação que tem de realizar para o seu negócio. Estas novas mensagens são orientadas por um processo ou comportamento e não por aquilo que pode ser feito com uma entidade. Estas mensagens podem corresponder a qualquer verbo de que necessite, tal como Escalar, Converter, Agendar, Encaminhar ou Aprovar. A adição destes verbos ajuda a fornecer um vocabulário mais rico para que possa definir fluentemente os seus processos de negócio. Pode aplicar este vocabulário mais rico a partir de clientes ou integrações, em vez de ter de escrever a ação nos clientes. Isto também facilita o processo, porque pode gerir e registar o sucesso ou o fracasso de toda a ação sob a forma de uma única unidade.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Mensagens configuráveis  
 Após a definição e ativação de uma mensagem, o programador pode utilizar essa mensagem como utilizaria qualquer uma das outras mensagens fornecidas pela plataforma. No entanto, há uma diferença significativa: agora as pessoas que não são programadores podem aplicar alterações ao que deveria ser feito quando essa mensagem é utilizada. Pode configurar a ação para modificar passos à medida que os seus processos de negócio mudam. Os códigos personalizados que utilizam essa mensagem só têm de ser alterados se os argumentos do processo mudarem.  
  
 Os plug-ins e processos de fluxo de trabalho continuam a proporcionar funcionalidades semelhantes para definir a automatização. Os processos de fluxo de trabalho continuam a permitir que os não programadores apliquem alterações. Contudo, a diferença está na forma como os processos de negócio são compostos e como os programadores podem escrever o respetivo código. As ações são mensagens que operam ao mesmo nível das outras mensagens fornecidas pela plataforma. Os programadores podem registar plug-ins para Ações.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Mensagens globais 
 
 Ao contrário dos fluxos de trabalho ou [plug-ins](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in) do Common Data Service, as ações não têm de estar associadas a uma entidade específica. Pode definir Ações "globais" que podem ser chamadas individualmente.

## <a name="next-steps"></a>Passos seguintes

[Criar uma ação personalizada](create-actions.md)  
  

