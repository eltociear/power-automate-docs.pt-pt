---
title: Monitorizar e gerir processos de fluxo de trabalho com o Power Apps | Microsoft Docs
ms.custom: ''
ms.date: 05/06/2018
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
ms.assetid: a987a803-4674-4eb0-87de-caefa003b1eb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e4042b71e6913f1008f506697fa39291b3cbf59a
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298270"
---
# <a name="monitor-and-manage-workflow-processes"></a>Monitorizar e gerir processos de fluxo de trabalho


Para monitorizar e gerir processos, tem de localizar o processo, avaliar o estado e executar as ações necessárias para resolver os problemas.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Fluxos de trabalho em segundo plano de monitorização  
 Os fluxos de trabalho em segundo plano geram registos de tarefas de sistema para monitorizar o estado. Poderá aceder a informações sobre estas tarefas de sistema em vários locais na aplicação:  
  
 **[Definições](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Tarefas de Sistema**  
 Isto irá incluir todos os tipos de tarefas de sistema. Terá de filtrar registos aos existentes em **Tipo de tarefa de sistema** é **Fluxo de trabalho**.  
  
 **O processo de fluxo de trabalho**  
 Abra a definição de fluxo de trabalho em segundo plano e aceda ao separador **Sessões de processo**. Isto irá mostrar apenas as tarefas de sistema para este fluxo de trabalho em segundo plano.  
  
 **A partir do registo**  
 Pode editar o formulário de entidade para que inclua a navegação da relação **Processos em segundo plano**. Isto irá mostrar todas as tarefas de sistema que foram iniciadas no contexto de registo.  
  
> [!NOTE]
>  Se uma tarefa de sistema assíncrona (fluxo de trabalho) falhar várias vezes consecutivas, o sistema começará a adiar a execução dessa tarefa para intervalos de tempo cada vez mais longos, para que o criador de aplicações ou administrador possa investigar e resolver o problema. Assim que o problema for resolvido, a tarefa começará a ser executada normalmente.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Ações na execução de fluxos de trabalho em segundo plano  
 Quando um as são executadas em segundo plano, tem opções para **Cancelar**, a **Pausa**, a **Adiar** funciona. Se colocou anteriormente um fluxo de trabalho, pode **Retomar** o mesmo.  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Fluxos de trabalho e ações em tempo real de monitorização  
 Os fluxos de trabalho e ações em tempo real não utilizam registos de tarefas de sistema que ocorram imediatamente. Todos os erros que ocorreram serão apresentados ao utilizador na aplicação com o título **Erro de processo de negócio**.  
  
 Não existem registos para operações êxito. Pode ativar o registo de erros verificar a opção de **Manter registos para tarefas de fluxo de trabalho com erros** na área de **Retenção do registo de fluxo de trabalho** na parte inferior do separador **Administração** a existência do processo.  
  
 Para ver o registo de erros para um processo específico, abra a definição de fluxo de trabalho ou a ação de tempo real e regressar ao separador **Sessão de Processo**. Isto irá mostrar todos os erros apenas para registar este processo.  
  
 Se pretender uma vista de todos os erros de qualquer processo, vá para **Localização Avançada** e crie uma vista que mostra erros na entidade de sessão do processo.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>Estado dos processos de fluxo de trabalho:  
 Quando vir uma lista de processos de fluxo de trabalho, todo o processo individual pode ter um dos seguintes **Estado** e valores de **Razão do estado** :  
  
|Condição|Razão do Estado|  
|-----------|-------------------|  
|Pronta|A Aguardar por Recursos|  
|Suspenso|A Aguardar|  
|Bloqueada|Em Curso<br /><br /> A Colocar em Pausa<br /><br /> A Cancelar|  
|Concluída|Com Êxito<br /><br /> Com falhas<br /><br /> Cancelada|  

## <a name="deleting-process-log-records"></a>Eliminar registos de processo

Se a sua organização utiliza fluxos de trabalho em segundo plano ou fluxos de processo de negócio que são executados com frequência, a quantidade de registos de processo pode tornar-se grande o suficiente para causar problemas de desempenho, bem como consumir quantidades significativas de armazenamento. Para eliminar os registos de processo não removidos suficientemente por uma das tarefas de eliminação de registos em massa padrão, pode utilizar a funcionalidade de tarefas de sistema de eliminação em massa para criar uma tarefa de eliminação de registos em massa personalizada.

1. Aceda a **Definições** > **Gestão de Dados** > **Eliminação de Registos em Massa**.
2. A partir da área **Eliminação de Registos em Massa**, selecione **Nova**. 
3. Na página inicial **Assistente de Eliminação em Massa**, selecione **Seguinte**.
4. Na lista de **Procurar**, selecione **Tarefas de sistema**.
5. As seguintes condições são utilizadas para criar uma tarefa de eliminação de registos em massa para eliminar registos de processo. 
 - **Tipo de Tarefa de Sistema Igual ao Fluxo de Trabalho**. Isto destina-se aos registos de fluxo de trabalho. 
 - **Estado Igual a Concluído**. Apenas os fluxos de trabalho concluídos são válidos para executar a tarefa.
 - **Razão do Estado Igual a Efetuado com Êxito**. Eliminar tarefas efetuadas com êxito, canceladas e não efetuadas.
 - **Concluído em Mais de X Dias 30**. Utilize o campo Concluído em para eliminar apenas os registos de processo de fluxo de trabalho com mais de 30 dias.
 ![custom-bulk-record-deletion.png](media/custom-bulk-record-deletion.png)
6. Clique em **Seguinte**.
7. Defina a frequência com que a tarefa de eliminação em massa será executada. Pode agendar a tarefa para ser executada em intervalos definidos ou criar uma tarefa de eliminação em massa única [Com a opção Imediatamente](#using-the-immediately-option). Neste exemplo, uma tarefa periódica é definida para ser executada no dia 21 de maio de 2018 e a cada 30 dias após esta data. 
![Opções de eliminação de registos em massa](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Com a opção Imediatamente

Tenha em atenção que tem a opção de executar uma eliminação em massa síncrona imediata dos registos ao selecionar a opção **Imediatamente**. Esta eliminação é realizada com a execução direta do SQL Server, em vez de passar cada registo através do pipeline de eventos de eliminação, o que pode reduzir o impacto sobre o desempenho do sistema. Esta é uma boa opção se quiser limpar rapidamente os registos de fluxo de trabalho adicionais em vez de ter a tarefa de eliminação em massa em espera na fila assíncrona para processamento. 

A opção **Imediatamente** será ativada quando as seguintes condições forem verdadeiras: 
- A tarefa de eliminação em massa destina-se à entidade de Tarefas de Sistema.
- Os critérios de pesquisa têm a condição Tipo de tarefa de sistema igual ao fluxo de trabalho. 
- O utilizador que cria a tarefa de eliminação em massa tem permissão global para o privilégio de eliminação na entidade AsyncOperation. A função de segurança do administrador de sistema tem este privilégio.  

A eliminação em massa síncrona só eliminará registos AsyncOperation no estado concluído. É processado um máximo de um milhão de registos para cada invocação. Terá de executar a tarefa múltiplas vezes se o ambiente tiver mais de um milhão de registos a remover.  
  
## <a name="next-steps"></a>Passos seguintes   
 [Melhores práticas para os processos de fluxo de trabalho](best-practices-workflow-processes.md) <br />

