---
title: Melhores práticas para gerir processos de fluxo de trabalho | Microsoft Docs
description: Compreender as formas recomendadas de utilizar fluxos de trabalho
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
author: Mattp123
ms.assetid: 34e34c33-003a-494f-858c-3d34aacb308c
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0b52fad0c5e8e1291dadf7422dafbb5902ee4646
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74356950"
---
# <a name="best-practices-for-workflow-processes"></a>Melhores práticas para os processos de fluxo de trabalho
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este tópico contém as melhores práticas para criar e gerir processos de fluxo de trabalho.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Evitar ciclos infinitos  
 É possível criar lógica num fluxo de trabalho que inicia um ciclo infinito, que consome recursos do servidor e afeta o desempenho. A situação típica em que um ciclo infinito pode ocorrer é se tiver um fluxo de trabalho configurado para iniciar quando um atributo é atualizado e, em seguida, atualizar esse atributo na lógica do fluxo de trabalho. A ação de atualização aciona o mesmo fluxo de trabalho que atualiza o registo e aciona o fluxo de trabalho continuamente.  
  
 Os fluxos de trabalho que cria incluem lógica para detetar e parar ciclos infinitos. Se um processo de fluxo de trabalho for executado mais do que um determinado número de vezes num registo específico num período de tempo curto, o processo falha com o seguinte erro: **Esta tarefa de fluxo de trabalho foi cancelada porque o fluxo de trabalho que a iniciou incluía um ciclo infinito. Corrija a lógica do fluxo de trabalho e tente novamente**. O limite de vezes é 16.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>Utilizar modelos de fluxo de trabalho  
 Se tiver fluxos de trabalho que sejam semelhantes e estiver a prever criar mais fluxos de trabalho que sigam o mesmo padrão, guarde o seu fluxo de trabalho como um modelo de fluxo de trabalho. Desta forma, da próxima vez que precisar de criar um fluxo de trabalho semelhante, crie o fluxo de trabalho com o modelo e evite introduzir todas as condições e ações a partir do zero.  
  
 Na caixa de diálogo **Criar Processo**, selecione **Novo processo baseado num modelo existente (selecione na lista)** .  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Utilizar fluxos de trabalho subordinados  
 Se aplicar a mesma lógica em ramos condicionais ou fluxos de trabalho diferentes, defina essa lógica como um fluxo de trabalho subordinado para que não tenha de replicar essa lógica manualmente em cada fluxo de trabalho ou ramo condicional. Isto ajuda a simplificar a manutenção dos seus fluxos de trabalho. Em vez de examinar vários fluxos de trabalho que possam aplicar a mesma lógica, pode atualizar apenas um fluxo de trabalho.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>Eliminar automaticamente tarefas de fluxo de trabalho concluídas
Para fluxos de trabalho em segundo plano (assíncronos), recomendamos que selecione a opção **Eliminar automaticamente as tarefas de fluxo de trabalho concluídas (para poupar espaço em disco)** na definição do fluxo de trabalho. Selecionar esta caixa permite que o sistema elimine registos de fluxos de trabalho de execuções com êxito para poupar espaço. Tenha em atenção que esses registos de execuções de fluxos de trabalho com falhas serão sempre guardados para resoluções de problemas.  

![Retenção de tarefas de fluxo de trabalho](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>Manter registos de tarefas de fluxo de trabalho com erros  
Para fluxos de trabalho que não são executados em segundo plano (síncronos), recomendamos que selecione a opção **Manter registos para tarefas de fluxo de trabalho com erros** na definição do fluxo de trabalho. Selecionar esta opção permite que os registos de execuções de fluxos de trabalho com falhas sejam guardados para resoluções de problemas. Os registos de execuções de fluxos de trabalho síncronos com êxito serão sempre eliminados para poupar espaço.   

![Opção Manter registos para fluxos de trabalho com falhas](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Limitar o número de fluxos de trabalho que atualizam a mesma entidade
Executar mais do que um fluxo de trabalho que atualize a mesma entidade pode causar problemas de bloqueio de recursos. Imagine vários fluxos de trabalho em execução em que todas as atualizações de oportunidades acionam uma atualização na conta associada. Várias instâncias destes fluxos de trabalho estão em execução e tentar atualizar o mesmo registo de conta em simultâneo pode resultar em problemas de bloqueio de recursos. Ocorrem falhas de fluxo de trabalho e é gravada uma mensagem de erro, tal como **Tempo Limite do SQL: não é possível obter um bloqueio no recurso _nome do recurso_** . 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Utilizar Notas para manter um registo das alterações  
 Quando editar fluxos de trabalho, deve utilizar o separador Notas e escrever a alteração que fez e por que motivo a fez. Isto permite que outra pessoa compreenda as alterações que efetuou.  
  
## <a name="next-steps"></a>Passos seguintes  
 [Workflow processes overview](workflow-processes.md)  (Descrição geral de processos de fluxo de trabalho)  
 [Configure workflow processes](configure-workflow-steps.md)  (Configurar processos de fluxo de trabalho)  
 [Monitorizar e gerir processos de fluxo de trabalho](monitor-manage-processes.md)
   
