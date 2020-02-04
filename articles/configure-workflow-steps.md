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
ms.openlocfilehash: 0380509b2677e2229ecd2a98a5f3b8dde4f9732c
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74361435"
---
# <a name="configure-workflow-stages-and-steps"></a>Configurar fases e passos do fluxo de trabalho
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Quando cria fluxos de trabalho, tem a opção de conter a lógica que pretende executar em fases e passos.  
  
 **Fases**  
 As fases facilitam a leitura da lógica de fluxo de trabalho e explicam a lógica de fluxo de trabalho. No entanto, as fases não afetam a lógica ou o comportamento de fluxos de trabalho. Se um processo tiver fases, todos os passos no processo têm de estar incluídos numa fase.  
  
 **Passos**  
 Os passos são uma unidade de lógica de negócio num fluxo de trabalho. Os passos podem incluir condições, ações, outros passos ou uma combinação destes elementos.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Ações que os processos de fluxo de trabalho podem executar  

 Os processos de fluxo de trabalho podem executar as ações indicadas na seguinte tabela.  
  
|Ação|Descrição|  
|------------|-----------------|  
|**Criar Registo**|Cria um novo registo para uma entidade e atribui os valores que escolher aos atributos.|  
|**Atualizar Registo**|Pode atualizar o registo em que o fluxo de trabalho está a ser executado, qualquer um dos registos ligados a esse registo com uma relação N:1 ou qualquer um dos registos criados pelos passos anteriores.|  
|**Atribuir Registo**|Pode atribuir o registo em que o fluxo de trabalho está a ser executado, qualquer um dos registos ligados a esse registo numa relação N:1 ou qualquer um dos registos criados por passos anteriores.|  
|**Enviar E-mail**|Envia um e-mail. Pode optar por criar uma nova mensagem de e-mail ou utilizar um modelo de e-mail configurado para a entidade do registo no qual o fluxo de trabalho está a ser executado ou em qualquer uma das entidades que tenha uma relação N:1 com a entidade ou a entidade dos registos criados por passos anteriores.|  
|**Iniciar Fluxo de Trabalho Subordinado**|Inicia um processo de fluxo de trabalho que foi configurado como um fluxo de trabalho subordinado.|  
|**Alterar Estado**|Altera o estado do registo em que o processo está a ser executado, qualquer um dos registos ligados a esse registo numa relação N:1 ou qualquer um dos registos criados por passos anteriores.|  
|**Parar Fluxo de Trabalho**|Interrompe o fluxo de trabalho atual. Pode definir um estado **Com Êxito** ou **Cancelado** e especificar uma mensagem de estado.<br /><br /> Quando os fluxos de trabalho em tempo real são configurados para um evento, parar um fluxo de trabalho com o estado cancelado irá impedir que a ação do evento seja concluída. Veja [Utilizar fluxos de trabalho em tempo real](configure-workflow-steps.md#BKMK_SynchronousWorkflows) para obter mais informações.|  
|**Passo Personalizado**|Os programadores podem criar passos de fluxo de trabalho personalizados que definem ações. Não existem passos personalizados disponíveis por predefinição.|  
  
### <a name="setting-record-values"></a>Definir valores de registo  

 Quando cria um registo, pode definir valores para o registo. Quando atualiza um registo, pode definir, anexar, incrementar, diminuir, multiplicar ou limpar os valores.  
  
 Quando seleciona **Definir Propriedades**, é aberta uma caixa de diálogo a mostrar o formulário predefinido da entidade.  
  
 Na parte inferior da caixa de diálogo, pode ver uma lista de campos adicionais que não estão presentes no formulário.  
  
 Para qualquer campo, pode definir um valor estático e isso será definido pelo fluxo de trabalho.  
  
 No lado direito da caixa de diálogo, o **Assistente de Formulários** oferece-lhe a capacidade de definir ou anexar valores dinâmicos a partir do contexto do registo atual. Isto inclui valores de registos relacionados que podem ser acedidos a partir das relações N:1 (muitos-para-um) da entidade.  
  
 As opções disponíveis no **Assistente de Formulários** dependem do campo que selecionou no formulário. Quando definir um valor dinâmico, verá um marcador de posição amarelo conhecido como "campo dinâmico" que mostra onde os dados dinâmicos serão incluídos. Se quiser remover o valor, selecione o campo dinâmico e elimine-o. Para campos de texto, pode utilizar uma combinação de dados dinâmicos e estáticos.  
  
 Com dados dinâmicos, não tem a certeza se um campo ou entidade relacionada tem o valor que pretende definir. Pode definir um número de campos para tentar definir o valor e ordená-los com as setas verdes. Se o primeiro campo não tiver dados, experimentamos o segundo campo e por aí adiante. Se nenhum dos campos tiver dados, pode especificar um valor predefinido para ser utilizado.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Definir condições para ações de fluxo de trabalho  

 Muitas vezes, as ações que aplica dependem de condições. Os processos de fluxo de trabalho fornecem várias formas de definir condições e criar lógica de ramificação para obter os resultados que pretende. Pode verificar os valores do registo em que o processo de fluxo de trabalho está a ser executado, quaisquer registos ligados a esse registo com uma relação N:1 ou valores dentro do próprio processo  
  
|Tipo de Condição|Descrição|  
|--------------------|-----------------|  
|**Condição de Verificação**|Uma declaração lógica "if-\<condição> then".<br /><br /> Pode verificar os valores atuais do registo em que o fluxo de trabalho está a ser executado, qualquer um dos registos ligados a esse registo numa relação N:1 ou qualquer um dos registos criados pelos passos anteriores. Com base nesses valores, pode definir passos adicionais quando a condição for verdadeira.<br /><br /> Na declaração "if-\<condição> then", pode utilizar os seguintes operadores: **Igual A**, **Não É Igual A**, **Contém Dados**, **Não Contém Dados**, **Por Baixo** e **Não Em**. **Nota:**  os operadores **Por Baixo** e **Não Em** são operadores hierárquicos. Só podem ser utilizados nas entidades que têm uma relação hierárquica definida. Se estiver a tentar utilizar estes operadores nas entidades que não têm a relação hierárquica definida, verá a mensagem de erro: "Está a utilizar um operador hierárquico numa entidade que não tem uma relação hierárquica definida. Torne a entidade hierárquica (ao marcar uma relação como hierárquica) ou utilize outro operador." Para obter mais informações sobre relações hierárquicas, veja [Definir e consultar dados hierárquicos relacionados](/powerapps/maker/common-data-service/define-query-hierarchical-data). A captura de ecrã que se encontra a seguir à tabela é um exemplo da definição do processo de fluxo de trabalho que utiliza os operadores hierárquicos **Abaixo De** e **Não Abaixo De**.|  
|**Ramo Condicional**|Numa declaração lógica "else-if-then", o editor utiliza o texto "Otherwise, if \<condição> then:"<br /><br /> Selecione uma condição de verificação que definiu anteriormente e pode adicionar um ramo condicional para definir passos adicionais quando a condição de verificação for falsa.|  
|**Ação Predefinida**|Numa declaração lógica "else", o editor utiliza o texto "Otherwise:"<br /><br /> Selecione uma condição de verificação, ramo condicional, condição de espera ou ramo de espera paralelo que definiu anteriormente e pode utilizar uma ação predefinida para definir passos para todos os casos que não correspondam aos critérios definidos nos elementos do ramo ou condição.|  
|**Condição de Espera**|Permite que um fluxo de trabalho em segundo plano se coloque a si mesmo em pausa até que os critérios definidos pela condição sejam cumpridos. O fluxo de trabalho começa de novo automaticamente quando os critérios na condição de espera forem cumpridos.<br /><br /> Os fluxos de trabalho em tempo real não podem utilizar condições de espera.|  
|**Ramo de Espera Paralelo**|Define uma condição de espera alternativa para um fluxo de trabalho em segundo plano com um conjunto correspondente de passos adicionais que são efetuados apenas quando os critérios iniciais são cumpridos. Pode utilizar ramos de espera paralelos para criar limites de tempo na sua lógica de fluxo de trabalho. Estes ajudam a impedir que o fluxo de trabalho aguarde indefinidamente até que os critérios definidos numa condição de espera sejam cumpridos.|  
|**Passo Personalizado**|Os programadores podem criar passos de fluxo de trabalho personalizados que definem condições. Não existem passos personalizados disponíveis por predefinição.|  
  
 A seguinte captura de ecrã contém um exemplo da definição do processo de fluxo de trabalho com os operadores hierárquicos **Abaixo De** e **Não Abaixo De**. No nosso exemplo, aplicamos dois descontos diferentes a dois grupos de contas. Em **Adicionar Passo**, selecionamos a **Condição de Verificação** para especificar a condição **if-then** que contém os operadores **Abaixo De** ou **Não Abaixo De**. A primeira condição **if-then** aplica-se a todas as contas que estão **Abaixo** da conta Alpine Ski House. Estas contas recebem 10% de desconto em serviços e bens comprados. A segunda condição **if-then** aplica-se a todas as contas **Não Abaixo** da conta Alpine Ski House e recebem 5% de desconto. Em seguida, selecione **Atualizar Registo** para definir a ação a ser executada com base na condição.  
  
 ![Processo de fluxo de trabalho com operadores Abaixo/Não Abaixo](media/wfp-under-not-under.PNG "Processo de fluxo de trabalho com operadores Abaixo/Não Abaixo")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Utilizar fluxos de trabalho em tempo real  

 Pode configurar fluxos de trabalho em tempo real, mas deve utilizá-los com cuidado. Geralmente, os fluxos de trabalho em segundo plano são recomendados porque permitem que o sistema os aplique à medida que os recursos no servidor estão disponíveis. Esta ação ajuda a simplificar o trabalho que o servidor tem de fazer e ajuda a manter o melhor desempenho para todas as pessoas que utilizam o sistema. A desvantagem é que as ações definidas pelos fluxos de trabalho em segundo plano não são imediatas. Não pode prever quando serão aplicadas, mas geralmente demoram alguns minutos. Para a maioria dos processos de negócio, isto não é problema porque as pessoas que utilizam o sistema não precisam de saber que o processo está em execução.  
  
 Utilize fluxos de trabalho em tempo real quando um processo de negócio exigir que alguém veja imediatamente os resultados do processo ou se quiser a possibilidade de cancelar uma operação. Por exemplo, pode querer predefinir determinados valores para um registo na primeira vez que for guardado ou pode querer garantir que alguns registos não são eliminados.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Conversão entre fluxos de trabalho em segundo plano e em tempo real  

 Pode converter um fluxo de trabalho em tempo real num fluxo de trabalho em segundo plano ao selecionar **Converter num fluxo de trabalho em segundo plano** na barra de ferramentas.  
  
 Pode converter um fluxo de trabalho em segundo plano num fluxo de trabalho em tempo real ao selecionar **Converter num fluxo de trabalho em tempo real** na barra de ferramentas. Se o fluxo de trabalho em segundo plano utilizar uma condição de espera, este torna-se inválido e não pode ativá-lo até remover a condição de espera.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Iniciar fluxos de trabalho em tempo real antes ou após alterar o estado  

 Quando configura **Opções para Processos Automáticos** para fluxos de trabalho em tempo real, as opções **Iniciar Quando** do evento de alteração de estado permitem-lhe selecionar **Após** ou **Antes** quando o estado muda. A opção predefinida é **Após**.  
  
 Quando seleciona **Antes**, está a dizer que pretende que a lógica no fluxo de trabalho seja aplicada antes de os dados mudarem e o estado ser guardado. Esta ação permite que verifique os valores antes que outra lógica seja aplicada após a operação e impede que outras lógicas sejam executadas. Por exemplo, pode ter lógica adicional numa ação de fluxo de trabalho personalizado ou plug-in que pode iniciar ações noutro sistema. Ao parar o processamento adicional, pode evitar casos em que os sistemas externos são afetados. Aplicar fluxos de trabalho em tempo real antes deste evento também significa que outras ações de plug-in ou fluxo de trabalho que podem ter guardado dados não precisam de ser "revertidas" quando a operação for cancelada.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Utilizar a ação Parar Fluxo de Trabalho com fluxos de trabalho em tempo real  

 Quando aplica uma ação **Parar Fluxo de Trabalho** num fluxo de trabalho, tem a opção de especificar uma condição de estado que pode ter o estado **Com Êxito** ou **Cancelado**. Quando define o estado como cancelado, impede a operação. Uma mensagem de erro que contém o texto da mensagem de estado da ação de interrupção será apresentada ao utilizador com o cabeçalho **Erro de Processo de Negócio**.  
  
## <a name="next-steps"></a>Próximos passos  
 [Create custom business logic with processes](guide-staff-through-common-tasks-processes.md)  (Criar lógica de negócio personalizada com processos)  
 [Workflow processes overview](workflow-processes.md)  (Descrição geral de processos de fluxo de trabalho)  
 [Monitorizar e gerir processos de fluxo de trabalho](monitor-manage-processes.md)   
 [Melhores práticas para os processos de fluxo de trabalho](best-practices-workflow-processes.md)
