---
title: Utilizar caixas de diálogo do Common Data Service para processos guiados (Preterido) | Microsoft Docs
description: As caixas de diálogo são os processos síncronos ou interativos que recolhem e processam informações com instruções passo a passo para orientar os utilizadores ao longo de um processo
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
ms.service: flow
ms.assetid: d17f8ae2-854b-4f67-a115-5a03d4f0b8ce
caps.latest.revision: 25
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 69b8d448a3bb2636f4804fe75645467ca6bd081d
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195871"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Utilizar caixas de diálogo do Common Data Service para processos guiados (Preterido)


[As caixas de diálogo foram preteridas](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). Deve substituir as caixas de diálogo por fluxos de processos de negócio ou aplicações baseadas em telas. Mais informações: [Substituir caixas de diálogo por fluxos de processos de negócio ou aplicações baseadas em telas](replace-dialogs.md) 

As caixas de diálogo são os processos síncronos ou interativos no Common Data Service que recolhem e processam informações com scripts passo a passo para orientar os utilizadores ao longo de um processo. Por exemplo, pode criar caixas de diálogo para atuarem como um guia para os seus representantes do suporte para resolução e escalamento de incidentes. Da mesma forma, pode criar caixas de diálogo para a uniformização dos processos de venda, tais como qualificação de oportunidades e pontuação de oportunidades potenciais.

## <a name="differences-between-workflows-and-dialogs"></a>Diferenças entre fluxos de trabalho e caixas de diálogo

A seguinte tabela fornece informações sobre as diferenças entre fluxos de trabalho e caixas de diálogo do Common Data Service.  


| Fluxos de Trabalho     |    Caixas de Diálogo      |
|---------------|--------------|
|                                                                                                  Pode ser iniciado por um utilizador ou pode ser automatizado.                                                                                                   |                                                                                          Tem de ser iniciado por um utilizador.                                                                                          |
|                                  São processos assíncronos ou em tempo real e não necessitam de intervenção do utilizador para serem executados até à sua conclusão. Os processos assíncronos são executados em segundo plano, enquanto os processos em tempo real são executados imediatamente.                                   | São processos em tempo real que necessitam da intervenção do utilizador para serem executados até à sua conclusão. Quando executa estes processos, uma interface do tipo assistente é apresentada para que possa efetuar as seleções adequadas para executar os processos. |
|                                                    A entidade que armazena os detalhes sobre um fluxo de trabalho assíncrono em execução é `AsyncOperation`, enquanto um `Process` é utilizado para um fluxo de trabalho em tempo real.                                                     |                                                       A entidade que armazena informações geradas por uma caixa de diálogo em execução é a entidade `ProcessSession`.                                                       |
|                  Os fluxos de trabalho suportam acionadores. Para obter uma lista dos acionadores suportados, veja [Supported Types, Triggers, and Entities for Processes](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes) (Tipos, Acionadores e Entidades Suportadas para Processos).                   |                                                                                   As caixas de diálogo não suportam acionadores.                                                                                    |
  
### <a name="see-also"></a>Veja também
[Substituir caixas de diálogo por fluxos de processos de negócio ou aplicações baseadas em telas](replace-dialogs.md)
