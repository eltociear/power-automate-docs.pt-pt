---
title: Utilizar controlos personalizados em fluxos do processo de negócio | Microsoft Docs
description: Saiba como utilizar controlos personalizados nos passos dos fluxos do processo de negócio.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: cd312fea655dfc652cf92a440801da2fdb17ebe4
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297038"
---
# <a name="use-custom-controls-in-business-process-flows"></a>Utilizar controlos personalizados em fluxos do processo de negócio

Os fluxos do processo de negócio proporcionam uma forma guiada para realizar o trabalho na forma de fases e passos. As fases indicam onde está no processo, enquanto os passos são itens de ação que levam a um resultado desejado. Os passos num processo de negócio estão vinculados a campos no Common Data Service. Além das visualizações padrão do tipo de campo (caixas de texto, listas pendentes e assim por diante), pode utilizar controlos personalizados para adicionar visualizações otimizadas (como controles de deslize, botões radiais, o controle do LinkedIn, etc.) aos passos dos fluxos do processo de negócio e proporcionar experiências envolventes para quem utiliza o seu processo de negócio.

## <a name="adding-custom-controls-to-a-business-process"></a>Adicionar controlos personalizados a um processo de negócio

Suponhamos que quer adicionar um botão radial ao passo **Orçamento Estimado** e um interruptor ao passo **Identificar Decisor** do processo de Vendas da Oportunidade Potencial. 

![Descrição Geral](./media/custom-controls/overview.png)

Aqui estão os passos que tem de seguir para adicionar controlos personalizados a um fluxo do processo de negócio:

1. Configure controlos personalizados num formulário de entidade relacionado.
1. Gere e exporte o formulário do fluxo do processo de negócio.
1. Copie as configurações do controlo personalizado para o formulário do fluxo do processo de negócio a partir do formulário de entidade relacionado.
1. Importe as personalizações novamente para o Common Data Service.

Siga estes passos para obter [instruções detalhadas sobre como adicionar controlos personalizados](https://powerusers.microsoft.com/t5/Power-Automate-Community-Blog/Preview-Custom-Controls-in-Business-Process-Flows/ba-p/263237) para os passos dos fluxos do processo de negócio.






