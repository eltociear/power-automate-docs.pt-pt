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
ms.openlocfilehash: c165213949d72fa9e7aacbc28d076969677a8802
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296664"
---
# <a name="use-actions"></a>Utilizar ações


As Ações abrem um leque de possibilidades para compor a lógica de negócio. Com as Ações, pode realizar operações como Criar, Atualizar, Eliminar, Atribuir ou Efetuar Ação. Internamente, uma ação cria uma mensagem personalizada. Os programadores referenciam estas ações como “mensagens”. Cada uma destas mensagens é baseada nas ações efectuadas num registo de entidade. Se o objetivo do processo for a criação de um registo, atualizá-lo e atribuí-lo, existem três passos separados. Cada passo é definida as capacidades de entidade e não necessariamente – o processo de negócio.  
  
Ações fornece a capacidade de definir uma única verbo (ou a mensagem) correspondente uma operação que necessita de efetuar para o seu negócio. Estas novas mensagens são premiadas por um processo ou comportamentos em vez do que podem ser efetuadas por uma entidade. Estas mensagens podem corresponder a verbos como escalam, converta, programam, encaminhar, ou aprovam – o que for necessário. A adição destas ajuda de verbos fornece um vocabulário mais avançada do utilizador fluente os processos de negócio. Pode aplicar o vocabulário mais avançada de clientes ou integrações em vez de necessita de criar uma ação nos clientes. Isto também facilita-a como pode controlar e registar o êxito ou falha da solução completa como uma unidade simples.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Mensagens configuráveis  
 Uma vez que uma ação é definida e ativada, um programador pode utilizar essa mensagem qualquer uma das outras mensagens fornecidas pela plataforma. No entanto, a diferença significativa está agora que uma pessoa que não seja um programador pode aplicar alterações ao que tem de ser efetuadas quando essa mensagem é utilizado. Pode configurar a ação para modificar passos como os processos de negócio são alterados. Código personalizado que utilizar essa mensagem não tem de ser alterado como os argumentos de processo não serão alterados.  
  
 Os processo e plug-ins de fluxo de trabalho continuam a fornecer capacidades semelhantes para definir a automatização. Os processos de fluxo de trabalho ainda fornece a capacidade de que não seja um programador aplicar alterações. Mas a diferença é o modo como os processos de negócio são compor e o modo como um programador pode escrever o código. Uma ação é uma mensagem que opera ao mesmo nível que qualquer uma das mensagens fornecidas pela plataforma. Os programadores podem registar plug-ins para Ações.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Mensagens globais 
 
 Ao contrário dos fluxos de trabalho do Common Data Service ou [plug-ins](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in), uma ação não tem de estar associada a uma entidade específica. Pode definir Ações "globais" que podem ser chamadas individualmente.

## <a name="next-steps"></a>Passos seguintes

[Criar uma ação personalizada](create-actions.md)  
  

