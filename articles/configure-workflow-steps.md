---
title: Configurar fases e passos do fluxo de trabalho no Power Apps | Microsoft Docs
description: Saiba como configurar passos do fluxo de trabalho
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 0b47dfd5-76db-464f-90c0-c64a0173dcdd
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5aa5d43617a0b60f02a0e8b7f58a597b2f0de5f3
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297258"
---
# <a name="configure-workflow-stages-and-steps"></a>Configurar fases e passos do fluxo de trabalho


Quando cria fluxos de trabalho, tem a opção de conter a lógica que pretende executar em fases e passos.  
  
 **Fases**  
 As fases de trabalho facilitam a leitura da lógica de fluxo de trabalho e explicam a lógica de fluxo de trabalho. No entanto, as fases não afectam a lógica nem o comportamento dos fluxos de trabalho. Se um processo tiver fases, quaisquer passos do processo têm de estar contidos numa fase.  
  
 **Passos**  
 Os passos são uma unidade de lógica de negócio num fluxo de trabalho. Os passos podem incluir condições, acções, outros passos ou uma combinação destes elementos.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Ações que os processos de fluxo de trabalho podem executar  

 Os processos de fluxo de trabalho podem efetuar as ações listadas na tabela seguinte.  
  
|Ação|Descrição|  
|------------|-----------------|  
|**Criar Registo**|Cria um novo registo para uma entidade e atribui os valores que selecionar a atributos.|  
|**Atualizar Registo**|Poderá atualizar o registo no qual fluxo de trabalho está em execução, quaisquer registos associados a esse registo numa relação N:1 ou quaisquer registos criado por passos anteriores.|  
|**Atribuir Registo**|Poderá atribuir o registo no qual fluxo de trabalho está em execução, quaisquer registos associados a esse registo numa relação N:1 ou quaisquer registos criado por passos anteriores.|  
|**Enviar Correio Eletrónico**|Envia uma mensagem de correio eletrónico. Pode optar por criar uma mensagem de correio eletrónico nova ou utilizar um modelo de correio eletrónico configurado para a entidade do registo em que o fluxo de trabalho está em executar, quaisquer entidades que tenham uma relação N:1 relação com a entidade ou a entidade para quaisquer registos criados por passos anteriores.|  
|**Iniciar Fluxo de Trabalho Subordinado**|Inicia um processo de fluxo de trabalho configurado como um fluxo de trabalho subordinado.|  
|**Alterar Estado**|Altera o estado do registo no qual processo está em execução, quaisquer registos associados a esse registo numa relação N:1 ou quaisquer registos criado por passos anteriores.|  
|**Parar Fluxo de Trabalho**|Para o fluxo de trabalho atual. Pode definir o estado de **Com êxito** ou de **Cancelado** e especificar uma mensagem de estado.<br /><br /> Quando os fluxos de trabalho em tempo real são configurados para um evento, parar um fluxo de trabalho com o estado cancelado impedirá que a ação de evento seja concluída. Consulte [utilizar fluxos de trabalho em tempo real](configure-workflow-steps.md#BKMK_SynchronousWorkflows) para obter mais informações.|  
|**Passo Personalizado**|Os programadores podem criar passos de fluxo de trabalho personalizados que definem ações. Não existem passos personalizados disponíveis por predefinição.|  
  
### <a name="setting-record-values"></a>Definir valores de registo  

 Quando cria um registo pode definir valores para o registo. Quando atualiza um registo pode definir, acrescentar, incrementar, decrementar, multiplicar ou limpar valores.  
  
 Quando seleciona **Definir propriedades**, é aberto um diálogo que mostra o formulário predefinido para a entidade.  
  
 Na parte inferior de diálogo pode ver uma lista dos campos adicionais não presentes no formulário.  
  
 Para qualquer campo, pode definir um valor estático que será definido pelo fluxo de trabalho.  
  
 No lado direito do diálogo, o **Assistente de formulários** fornece a capacidade de ajustar ou acrescentar valores dinâmicos ao contexto do registo atual. Isto inclui valores de registos relacionados que podem ser acedidos a partir das relações N:1 (muitos para um) para a entidade.  
  
 As opções disponíveis no **Assistente de Formulários** dependem do campo que selecionou no formulário. Quando define um valor dinâmico, verá um marcador de posição amarelo conhecido como “campo dinâmico” que mostra onde os dados dinâmicos serão incluídos. Se pretender remover o valor, selecione o campo dinâmico e elimine-o. Para campos de texto, poderá utilizar uma combinação de dados estáticos ou dinâmicos.  
  
 Com valores dinâmicos não tem a certeza de que um campo ou uma entidade relacionada tem o valor que pretende definir. Pode definir um número de campos para experimentar e definir o valor e ordená-lo utilizando as setas verdes. Se o primeiro campo não tiver dados, será tentado o segundo campo e assim consecutivamente. Se nenhum dos campos tiver dados, pode especificar um valor predefinido a utilizar.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Definir condições para ações de fluxo de trabalho  

 As ações que aplicará frequentemente dependem das condições. Os processos de fluxo de trabalho fornecem várias maneiras para definir condições definidas e criar lógica de ramificação para obter os resultados pretendidos. Pode verificar os valores do registo contra o qual o processo de fluxo de trabalho está a ser executado, qualquer dos registos associados a esse registo numa relação N:1 ou valores do processo propriamente dito  
  
|Tipo de Condição|Descrição|  
|--------------------|-----------------|  
|**Condição de Verificação**|Uma declaração lógica "if-\<condition> then".<br /><br /> Poderá verificar os valores atuais do registo no qual fluxo de trabalho está em execução, quaisquer registos associados a esse registo numa relação N:1 ou quaisquer registos criados por passos anteriores. Com base nestes valores pode definir passos adicionais quando a condição é true.<br /><br /> Na instrução "if-\<condition> then", poderá utilizar os operadores seguintes: **É Igual A**, **Não é igual a**, **Contém dados**, **Não contém dados**, **Em** e **Não em**. **Nota:** Os operadores **Em** e **Não Em** são operadores hierárquicos. Só podem ser utilizados em entidades que tenham uma relação hierárquica definida. Se está a tentar utilizar estes operadores em entidades que não tenham relação hierárquica definida, verá a mensagem de erro: “Está a utilizar um operador hierárquico numa entidade que não tem uma relação hierárquica definida. Torne a entidade hierárquica (ao marcar uma relação como hierárquica) ou utilize outro operador." Para obter mais informações sobre relações hierárquicas, veja [Definir e consultar dados hierárquicos relacionados](/powerapps/maker/common-data-service/define-query-hierarchical-data). Um captura de ecrã que monitoriza a tabela é um exemplo de definição do processo de fluxo de trabalho utilizando **Em** e os operadores hierárquicas de **Não em** .|  
|**Ramo Condicional**|Uma declaração “else-if-then " lógica, o editor utiliza o texto “Otherwise, if \<condition> then:”<br /><br /> Selecione uma condição de verificação definida anteriormente e poderá adicionar um ramo condicional para definir passos adicionais quando a condição de verificação devolve false.|  
|**Ação Predefinida**|Uma declaração "else" lógica. o editor utiliza texto “Caso contrário:”<br /><br /> Selecione uma condição de verificação, ramo condicional, condição de espera ou ramo de espera paralelo definido anteriormente e pode utilizar uma ação predefinida para definir passos para todos os casos que não correspondem aos critérios definidos nos elementos de condição ou de ramo.|  
|**Condição de Espera**|Permite que um fluxo de trabalho de segundo plano seja interrompido até os critérios definidos pela condição serem correspondidos. O fluxo de trabalho recomeça automaticamente quando os critérios especificados na condição de espera tiverem sido cumpridos.<br /><br /> Os fluxos de trabalho em tempo real não podem utilizar condições de espera.|  
|**Ramo de Espera Paralelo**|Define uma condição de espera alternativa para um fluxo de trabalho de segundo plano com um conjunto correspondente de passos adicionais que só são executados quando o critério inicial é satisfeito. Pode utilizar ramos de espera paralelos para criar limites de tempo na lógica de fluxo de trabalho. Estes ajudam a impedir que o fluxo de trabalho aguarde indefinidamente até que os critérios definidos numa condição de espera tenham sido cumpridos.|  
|**Passo Personalizado**|Os programadores podem criar passos de fluxo de trabalho personalizados que definem condições. Não existem passos personalizados disponíveis por predefinição.|  
  
 A captura de ecrã seguinte contém um exemplo da definição do processo de fluxo de trabalho com os operadores hierárquicos **Em** e **Não em** . No nosso exemplo, as aplicamos dois descontos diferentes em dois grupos de contas. Em **Adicionar passo**, iremos selecionamos **Condição de verificação** para especificar condição de **se em** que contém os operadores de **Em** ou de **Não em** . A primeira condição de **se em** aplicam-se a todas as contas existentes **Em** a conta alpina de casa de esqui. Essas contas recebem um desconto de 10% em bom ter em e serviços. A segunda condição de **se em** aplicam-se a todas as contas existentes **Não em** a conta alpina de casa de esqui e recebem um desconto de 5%. Na, selecionamos **Atualizar registo** para definir a ação a efetuar baseamos a condição.  
  
 ![Processo de fluxo de trabalho com operadores Em/Não em](media/wfp-under-not-under.PNG "Processo de fluxo de trabalho com operadores Em/Não em")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Utilizar fluxos de trabalho em tempo real  

 Poderá configurar fluxos de trabalho em tempo real mas deverá utilizá-los com cuidado. Os fluxos de trabalho em segundo plano são geralmente recomendados porque permitem que o sistema os aplique à medida que os recursos estão disponíveis no servidor. Isto ajuda a otimizar o trabalho que o servidor necessita de fazer e ajuda a manter o melhor desempenho para todas as pessoas que utilizem o sistema. O inconveniente é que as ações definidas por fluxos de trabalho em segundo plano não são instantâneas. Não pode prever quando serão aplicadas, mas geralmente isto demora alguns minutos. Para a maioria da automatização de processos de negócio isto é aceitável porque as pessoas que utilizam o sistema não têm de ter noção de que o processo está em execução.  
  
 Utilize fluxos de trabalho em tempo real quando um processo de negócio requer que alguém veja imediatamente os resultados do processo ou se pretende ter a capacidade para cancelar uma operação. Por exemplo, poderá querer configurar determinados valores predefinidos para um registo quando este é guardado pela primeira vez ou certificar-se de que alguns registos não serão eliminados.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Conversão entre fluxos de trabalho em tempo real e em segundo plano  

 Pode alterar um fluxo de trabalho em tempo real num fluxo de trabalho em segundo plano escolhendo **Converter num fluxo de trabalho em segundo plano** na barra de ferramentas.  
  
 Pode alterar um fluxo de trabalho em segundo plano num fluxo de trabalho em tempo real escolhendo **Converter num fluxo de trabalho em tempo real** na barra de ferramentas. Se o fluxo de trabalho em segundo plano utilizar condições de espera, será inválido e não o poderá ativar enquanto não remover a condição de espera.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Iniciar fluxos de trabalho em tempo real antes ou depois de alterações do estado  

 Quando configura **Opções para processos automáticos** para fluxos de trabalho em tempo real, as opções de **Iniciar quando** do evento de alterações do estado permitem-lhe selecionar **Depois** ou **Antes** para o momento em que o estado é alterado. A opção predefinida é **Depois**.  
  
 Quando seleciona **Antes** está a dizer que pretende que a lógica no fluxo de trabalho seja aplicada antes dos dados que alteram o estado sejam guardados. Este procedimento fornece a capacidade de verificar os valores antes de outra lógica ser aplicada depois da operação e impedir que uma lógica adicional seja executada. Por exemplo, pode ter lógica adicional num plug-in ou numa ação de fluxo de trabalho personalizada que poderá iniciar ações noutro sistema. Ao parar qualquer processamento adicional pode evitar casos em que o sistema externo é afetado. Aplicar fluxos de trabalho em tempo real antes deste evento também significa que outras ações de fluxo de trabalho ou de plug-in que podem ter dados guardados não tenham de ser "revertidas" quando a operação for cancelada.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Utilizar a ação Parar Fluxo de Trabalho com fluxos de trabalho em tempo real  

 Quando aplica uma ação **Parar fluxo de trabalho** num fluxo de trabalho tem a opção para especificar uma condição de estado que pode ser **Com êxito** ou **Cancelado**. Quando define o estado como cancelado, impede a operação. Uma mensagem de erro que contém o texto da mensagem de estado da ação de paragem será apresentada ao utilizador com o título **Erro de processo de negócio**.  
  
## <a name="next-steps"></a>Passos seguintes  
 [Create custom business logic with processes](guide-staff-through-common-tasks-processes.md)  (Criar lógica de negócio personalizada com processos)  
 [Workflow processes overview](workflow-processes.md)  (Descrição geral de processos de fluxo de trabalho)  
 [Monitorizar e gerir processos de fluxo de trabalho](monitor-manage-processes.md)   
 [Melhores práticas para processos de fluxo de trabalho](best-practices-workflow-processes.md)
