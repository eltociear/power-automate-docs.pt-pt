---
title: Configurar ações para fluxos de trabalho no Power Apps | MicrosoftDocs
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
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
caps.latest.revision: 19
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: cba86e3e10591bb5e1ac36a68840ff7954146329
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296972"
---
# <a name="configure-custom-actions-from-a-workflow"></a>Configurar ações personalizadas a partir de um fluxo de trabalho


Pode ativar uma ação personalizada de um fluxo de trabalho sem escrever código. Mais informações: [Invocar ações personalizadas de um fluxo de trabalho](invoke-custom-actions-workflow-dialog.md).  
  
 Também poderá criar uma ação para que um programador a possa utilizar no código ou poderá ter de editar uma ação que foi definida anteriormente. Como processos de fluxo de trabalho, considere o seguinte:  
  
-   O que deve a ação fazer?  
  
-   Em que condições deve a ação ser executada?  
  
 
Ao contrário dos processos de fluxo de trabalho, não tem de definir as seguintes opções:  
  
- **Iniciar quando**: Ações começam quando o código chama a mensagem gerado mesmo.  
  
- **Âmbito**: As ações são sempre executado no contexto do utilizador de chamadas.  
  
- **É executada em segundo plano**: As ações são sempre fluxos de trabalho em tempo real.  
  
As ações também têm algo que os processos de fluxo de trabalho não têm: argumentos de entrada e saída. Mais informações: [Definir argumentos do processo](configure-actions.md#BKMK_DefineProcessArgs)  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Criar uma ação  
  
> [!IMPORTANT]
>  Se estiver a criar uma ação que fará parte de uma solução que será distribuída, crie essa ação no contexto da solução. Aceda a **[Definições](/powerapps/maker/model-driven-apps/advanced-navigation#settings)** > **Soluções** e localize a solução não gerida da qual a ação fará parte. Em seguida, na barra de menus, selecione **Novo** > **Processo**. Isto assegura que o prefixo de personalização associado ao nome da ação será consistente com os outros componentes na solução. Depois de criar uma ação como, não pode alterar o prefixo.  
  
 Como os processos de fluxo de trabalho, as ações têm as seguintes propriedades na caixa de diálogo **Criar Processo**.  
  
 **Nome do processo**  
 Depois de introduzir um nome para o processo, será criado um nome exclusivo removendo todos os espaços ou carateres especiais do nome do processo.  
  
 **Categoria**  
 Esta propriedade estabelece que é um processo de ação. Não pode alterar isto depois de guardar o processo.  
  
 **Entidade**  
 Com processos ações, pode selecionar uma entidade fornecer contexto para o fluxo de trabalho exatamente como outros tipos de processos, mas também tem a opção de selecionar **Não (de)**. Utilize esta opção se a ação não necessita que o contexto de uma entidade específica. Não pode alterar isto depois de guardar o processo.  
  
 **Tipo**  
 Utilize esta propriedade para escolher se pretende criar uma nova ação de raiz ou começar a partir de um modelo existente.  
  
<a name="edit"></a>   
## <a name="edit-an-action"></a>Editar uma ação  
 Tem de desativar processos antes dos poder editar.  
  
 Pode editar uma ação criada como parte de uma solução não gerida ou incluída numa solução instalada na organização. Se a solução é uma solução gerida, não poderá editá-la. O fabricante de soluções tem a opção para editar as propriedades geridas de modo a que a solução instalada com uma solução gerida não pode ser editado.  
  
 Quando uma ação é guardada, um nome exclusivo é gerado baseado no nome do processo. Este nome tem o prefixo de personalização adicionado do fabricante de soluções. Este é o nome da mensagem que um programador utilizar no código.  
  
 Para editar uma ação tem as seguintes opções:  
  
 **Nome do Processo**  
 Após o processo criado é o nome exclusivo gerado é o nome do processo, pode editar o nome do processo. Poderá pretender aplicar uma convenção de nomenclatura para facilitar a localização de processos específicos.  
  
 **Nome Exclusivo**  
 Quando uma ação é guardada, um nome exclusivo é gerado baseado no nome do processo. Este nome tem o prefixo de personalização adicionado do fabricante de soluções. Este é o nome da mensagem que um programador utilizar no código. Não altere este nome exclusivo se o processo foi ativado e o código é a localização nos contactar a ação com este nome.  
  
> [!IMPORTANT]
>  Quando a ação é ativada e o código esteja escrito para utilizar um nome, o nome não tem de ser alterado sem também alterar o código que referencia a mesma.  
  
 **Ativar reversão**  
 Normalmente, os processos que suportam transações “anulam" (ou revertem) a operação se a qualquer parte desta falhar. Existem algumas exceções a este. Algumas ações que os programadores podem criar código em iniciou a ação poderão não suporta transações. Por exemplo, se o código efetua ações em outros sistemas que são além de acesso da transação. Estes não poderão ser revertidos pela ação em execução numa aplicação. Algumas mensagens na plataforma não suportam transações. Mas tudo o que pode fazer com apenas a interface de utilizador de ação suporta transações. As ações que fazem parte de um fluxo de trabalho em tempo real são consideradas a transação, mas com ações que optar ativamente a sessão desta.  
  
 Tem de procurar com o programador que irá utilizar esta mensagem para determinar se deve ser ou não na transação. Normalmente, uma ação tem de ser a transação se as ações efectuadas pelo processo de negócio não adequadas a menos que todos são concluídas com êxito. A instância está transferir clássico fundos entre duas contas bancárias. Se sair de fundos uma conta tem de depositá-los em outra. Se qualquer um falha, não têm falhar.  
  
> [!NOTE]
>  Não poderá ativar a reversão se uma ação personalizada for invocada diretamente a partir de um fluxo de trabalho. Poderá ativar a a reversão se uma ação for acionada por uma mensagem de serviços Web do Power Apps.  
  
 **Ativar Como**  
 Como os processos, poderá ativar o processo como modelo e utilizar como ponto de partida avançada para os processos que sigam um padrão semelhante.  
  
 **Definir Argumentos do Processo**  
 Nesta área, especificará os dados que a ação prevê iniciar, bem como os dados que serão passados para fora da ação. Mais informações: [Definir argumentos do processo](configure-actions.md#BKMK_DefineProcessArgs)  
  
 **Adicione fases e condições, ações**  
 Tal como acontece com outros processos, deve especificar as ações a realizar e o momento em que serão realizadas. Mais informações: [Adicionar fases, condições e ações](configure-actions.md#BKMK_AddStagesConditionsAndActions)

<a name="BKMK_DefineProcessArgs"></a>   
### <a name="define-process-arguments"></a>Definir argumentos do processo  
 Quando um programador utiliza uma mensagem, poderá começar com alguns dados que podem ser transmitidos para a mensagem. Por exemplo, para criar um novo registo de, poderá ser o valor do título do incidente que é transmitido como um argumento de entrada.  
  
 Quando a mensagem estiver concluída, o programador poderá ter de transmitir alguns dados que foram alterados ou gerados pela mensagem para outra operação no código. Estes dados são o argumento de saída.  
  
 Os argumentos de entrada e saída de têm de ter um nome, tipo, e qualquer informação sobre se o incidente é necessário sempre. Também pode fornecer uma descrição.  
  
 O nome da mensagem e informações sobre todos os incidentes do processo “representam a subscrição” da mensagem. Quando uma ação é ativada e está a ser utilizada no código, a assinatura não deve ser alterada. Se esta subscrição for alterada, qualquer código que utilizar a mensagem irá falhar. A única à exceção é possível alterar um dos parâmetros de modo a não se necessita sempre.  
  
 Poderá alterar a ordem dos argumentos ao ordená-los ou movê-los para cima ou para baixo porque os argumentos estão identificados por nome, não pela ordem. Além disso, alterar a descrição não quebra o código ao utilizar a mensagem.  
  
#### <a name="action-process-argument-types"></a>Tipos de argumento do processo de ação  
 A tabela seguinte descreve os tipos de argumento do processo de ação.  
  
|Tipo|Descrição|  
|----------|-----------------|  
|Booleano|Um valor de `true` ou de `false`.|  
|DateTime|Um valor que armazena informações data e hora.|  
|Decimal|O número a precisão decimal. A precisão utilizado quando é extremamente importantes.|  
|Entidade|Um registo para a entidade especificada. Quando seleciona Entidade, a lista pendente é ativada e permite-lhe selecionar o tipo de entidade.|  
|EntityCollection|Conjunto de registos de entidade.|  
|EntityReference|Um objeto que contém o nome, o ID, e o tipo de um registo de entidade que o identifica exclusivamente. Quando seleciona EntityReference, a lista pendente é ativada e permite-lhe selecionar o tipo de entidade.|  
|Flutuante|O número a precisão decimal. Utilizado quando os dados vierem de uma medida que não seja absolutamente necessita.|  
|Número Inteiro|Um número inteiro.|  
|Dinheiro|Um valor que armazena dados para o montante de dinheiro.|  
|Picklist|Um valor que representa uma opção para um atributo OptionSet.|  
|String|Um valor de texto.|  
  
> [!NOTE]
> os valores do argumento de**EntityCollection** não podem ser definidas na interface de utilizador para condições ou ações. Estes valores são fornecidos para que os programadores os utilizem em código personalizado. Mais informações: [Create your own actions](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) (Criar suas próprias ações) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Adicionar fases e passos  
 As ações são um tipo de processo muito semelhante aos fluxos de trabalho em tempo real. Quaisquer passos que poderão ser utilizadas em fluxos de trabalho em tempo real podem ser utilizadas em ações. Para obter informações sobre os passos que podem ser utilizados para fluxos de trabalho e ações em tempo real, consulte [Fases e passos de fluxo de trabalho](configure-workflow-steps.md)..  
  
 Além dos passos que podem ser utilizados para fluxos de trabalho em tempo real, as ações também têm o passo **Atribuir Valor**.   Em ações, apenas podem ser utilizados para definir argumentos de saída. Pode utilizar o assistente de formulários para definir argumentos de saída para valores específicos ou, mais provavelmente, para valores provenientes do registo no qual a ação está a ser executada, registos relacionados com esse registo com uma relação muitos-para-um, registos criados num passo anterior ou valores que fazem parte do próprio processo.  
  
## <a name="next-steps"></a>Passos seguintes  
 [Acções](actions.md)  

 [Invocar ações personalizadas a partir de um fluxo de trabalho](invoke-custom-actions-workflow-dialog.md)   
 [Monitorizar fluxos de trabalho e ações em tempo real](monitor-manage-processes.md#BKMK_MonitorSyncWorkflows)
 
 
