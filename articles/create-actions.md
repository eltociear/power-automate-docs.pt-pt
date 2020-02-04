---
title: Criar uma ação personalizada | Microsoft Docs
description: Utilize ações personalizadas quando quiser automatizar uma série de comandos no sistema. As ações expandem o vocabulário disponível para os programadores expressarem os processos de negócios.
ms.custom: ''
ms.date: 08/06/2018
ms.reviewer: matp
ms.service: flow
ms.topic: article
author: msftman
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 140afe0c93b85363b8dab9658838d985ab9e786c
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74361481"
---
# <a name="create-a-custom-action"></a>Criar uma ação personalizada
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Utilize ações personalizadas quando quiser automatizar uma série de comandos no sistema. As ações expandem o vocabulário disponível para os programadores expressarem os processos de negócios. Os verbos principais, como Criar, Atualizar, Eliminar e Atribuir, são fornecidos pelo sistema. Uma Ação utiliza esses verbos principais para criar verbos mais expressivos, como Aprovar, Escalar, Encaminhar ou Agendar. Se a definição de um processo de negócio mudar, alguém que não seja um programador pode editar a ação personalizada para que o código não tenha de ser alterado.  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Criar uma ação  
  
> [!IMPORTANT]
>  Se estiver a criar uma ação que fará parte de uma solução que será distribuída, crie essa ação no contexto da solução. Aceda a **[Definições](/powerapps/maker/model-driven-apps/advanced-navigation#settings)**  > **Soluções** e localize a solução não gerida da qual a ação fará parte. Em seguida, na barra de menus, selecione **Novo** > **Processo**. Isto garante que o prefixo de personalização associado ao nome da ação será consistente com outros componentes da solução. Depois de criar a ação, não pode alterar o prefixo.  
  
 Tal como no caso dos processos de fluxo de trabalho, as ações têm as seguintes propriedades na caixa de diálogo **Criar Processo**.  
  
 **Nome do processo**  
 Depois de introduzir um nome para o processo, será criado um nome exclusivo para o processo ao remover todos os espaços ou carateres especiais do nome do mesmo.  
  
 **Categoria**  
 Esta propriedade determina que se trata de um processo de ação. Não pode alterar esta propriedade depois de guardar o processo.  
  
 **Entidade**  
 No caso dos processos de ações, pode selecionar uma entidade para fornecer contexto ao fluxo de trabalho tal como acontece com outros tipos de processo, mas também pode selecionar **Nenhum (global)** . Utilize esta opção se a ação não exigir o contexto de uma entidade específica. Não pode alterar esta propriedade depois de guardar o processo.  
  
 **Tipo**  
 Utilize esta propriedade para optar por criar uma nova ação do zero ou começar a partir de um modelo existente.  
 
Ao contrário dos processos de fluxo de trabalho, não precisa de definir as seguintes opções:  
  
- **Iniciar Quando**: as ações começam quando o código chama a mensagem gerada para as mesmas.  
  
- **Âmbito**: as ações são sempre executadas no contexto do utilizador que efetua a chamada.  
  
- **Executar em segundo plano**: as ações são sempre fluxos de trabalho em tempo real.  
  
As ações também têm algo que os processos de fluxo de trabalho não têm: argumentos de entrada e saída.

> [!NOTE]
> Pode ativar uma ação personalizada de um fluxo de trabalho sem escrever código. Mais informações: [Invocar ações personalizadas de um fluxo de trabalho](invoke-custom-actions-workflow-dialog.md).
 
<a name="edit"></a>   
## <a name="edit-an-action"></a>Editar uma ação  
 Antes de editar os processos, tem de os desativar.  
  
 Pode editar uma ação que foi criada como parte de uma solução não gerida ou que está incluída numa solução instalada na sua organização. Se a solução for gerida, poderá não conseguir editar a ação. O fabricante de soluções pode editar as propriedades geridas de forma a que a ação instalada com uma solução gerida não possa ser editada.  
  
 Quando se guarda uma ação, é gerado um nome exclusivo com base no nome do processo. Este nome exclusivo inclui o prefixo de personalização do fabricante de soluções. Este é o nome da mensagem que o programador utilizará no respetivo código.  
  
 Ao editar uma ação, tem as seguintes opções:  
  
 **Nome do Processo**  
 Depois de o processo ser criado e de o nome exclusivo ser gerado a partir do nome do processo, poderá editar o nome do processo. É recomendado aplicar uma convenção de nomenclatura para facilitar a localização de processos específicos.  
  
 **Nome Exclusivo**  
 Quando se guarda uma ação, é gerado um nome exclusivo com base no nome do processo. Este nome exclusivo inclui o prefixo de personalização do fabricante de soluções. Este é o nome da mensagem que o programador utilizará no respetivo código. Não altere este nome exclusivo se o processo tiver sido ativado e o código estiver à espera de chamar a ação com recurso a este nome.  
  
> [!IMPORTANT]
>  Após a ativação da ação e depois de o código ser escrito de forma a utilizar um nome exclusivo, este último só pode ser alterado se também se alterar o código que faz referência ao mesmo.  
  
 **Ativar a reversão**  
 Geralmente, os processos que suportam transações "anularão" (ou reverterão) toda a operação se alguma parte das mesmas falhar. No entanto, existem algumas exceções. Algumas ações que os programadores poderão fazer em código iniciado pela ação poderão não suportar transações. Por exemplo, se o código realizar ações noutros sistemas que não estão incluídos no âmbito da transação. A ação executada numa aplicação não pode reverter essas transações. Algumas mensagens na plataforma não suportam transações. Contudo, tudo o que puder fazer exclusivamente com a interface de utilizador da ação suportará transações. Todas as ações que fazem parte de um fluxo de trabalho em tempo real são consideradas como estando em transação mas, no caso das ações, pode optar ativamente por que tal não aconteça.  
  
 Deve consultar o programador que utilizará esta mensagem para determinar se esta tem de estar ou não em transação. Geralmente, as ações devem estar em transação se as ações executadas pelo processo de negócio só fizerem sentido se todas as ações forem concluídas com sucesso. O exemplo clássico é a transferência de fundos entre duas contas bancárias. Se retirar fundos de uma conta, tem de os depositar na outra. Se uma das duas ações falhar, ambas terão de falhar.  
  
> [!NOTE]
>  Não é possível ativar a reversão se uma ação personalizada for invocada diretamente a partir de um fluxo de trabalho. Poderá ativar a reversão se uma ação for acionada por uma mensagem dos serviços Web do Power Apps.  
  
 **Ativar Como**  
 Tal como acontece com todos os processos, pode ativar o processo como um modelo e utilizá-lo como ponto de partida avançado para os processos que seguem um padrão semelhante.  
  
 **Definir Argumentos do Processo**  
 Nesta área, especificará os dados que a ação prevê iniciar, bem como os dados que serão passados para fora da ação. Mais informações: [Definir argumentos do processo](#define-process-arguments)  
  
 **Adicionar fases e passos**  
 Tal como acontece com outros processos, deve especificar as ações a realizar e o momento em que serão realizadas. Mais informações: [Adicionar fases e passos](#add-stages-and-steps)

<a name="BKMK_DefineProcessArgs"></a>   
## <a name="define-process-arguments"></a>Definir argumentos do processo  
 Quando um programador utiliza uma mensagem, pode começar com alguns dados que podem passar para a mensagem. Por exemplo, para criar um novo registo de incidente, poderá ser o valor do título do incidente que é passado como argumento de entrada.  
  
 Após a conclusão da mensagem, o programador poderá ter de transmitir alguns dados que foram alterados ou gerados pela mensagem para outra operação no código do mesmo. Estes dados são o argumento de saída.  
  
 Tanto os argumentos de entrada como de saída têm de ter um nome, um tipo e algumas informações sobre se o argumento é sempre necessário ou não. Também pode fornecer uma descrição.  
  
 O nome da mensagem e as informações sobre todos os argumentos do processo são a "assinatura" da mensagem. Depois de a ação ser ativada e estar a ser utilizada no código, a assinatura não pode mudar. Se esta assinatura mudar, qualquer código que utilize a mensagem falhará. A única exceção a este facto poderá ser a alteração de um dos parâmetros para que não seja sempre necessário.  
  
 Pode alterar a ordem dos argumentos ao ordená-los ou movê-los para cima ou para baixo, dado que os argumentos são identificados pelo nome e não pela ordem. Além disso, a alteração da descrição não quebrará o código que utiliza a mensagem.  
  
### <a name="action-process-argument-types"></a>Tipos de argumentos de processos de ação  
 A tabela abaixo descreve os tipos de argumentos de processos de ação.  
  
|Tipo|Descrição|  
|----------|-----------------|  
|Booleano|Um valor `true` ou `false`.|  
|DateTime|Um valor que armazena informações de data e hora.|  
|Decimal|Um valor numérico com precisão decimal. Utilizado quando a precisão é extremamente importante.|  
|Entity|Um registo da entidade especificada. Quando selecionar Entidade, o menu pendente será ativado e irá permitir-lhe selecionar o tipo de entidade.|  
|EntityCollection|Uma coleção de registos de entidade.|  
|EntityReference|Um objeto que contém o nome, o ID e o tipo de um registo de entidade que o identifica exclusivamente. Quando selecionar EntityReference, o menu pendente será ativado e irá permitir-lhe selecionar o tipo de entidade.|  
|Float|Um valor numérico com precisão decimal. Utilizado quando os dados provêm de uma medida que não é absolutamente precisa.|  
|Integer|Um número inteiro.|  
|Money|Um valor que armazena dados relativos a uma quantia em dinheiro.|  
|Picklist|Um valor que representa uma opção para um atributo OptionSet.|  
|String|Um valor de texto.|  
  
> [!NOTE]
> Não é possível definir valores do argumento **EntityCollection** na interface de utilizador para condições ou ações. Estes valores são fornecidos para que os programadores os utilizem em código personalizado. Mais informações: [Criar as suas próprias ações](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Adicionar fases e passos  
 As ações são um tipo de processo muito semelhante aos fluxos de trabalho em tempo real. Todos os passos que podem ser utilizados em fluxos de trabalho em tempo real podem ser utilizados em ações. Para obter informações sobre os passos que podem ser utilizado em fluxos de trabalho em tempo real e em ações, veja [Workflow stages and steps](configure-workflow-steps.md) (Fases e passos do fluxo de trabalho).  
  
 Para além dos passos que podem ser utilizados em fluxos de trabalho em tempo real, as ações também têm o passo **Atribuir Valor**.  Nas ações, estes só podem ser utilizados para definir argumentos de saída. Pode utilizar o assistente de formulários para definir argumentos de saída para valores específicos ou, mais provavelmente, para valores provenientes do registo no qual a ação está a ser executada, registos relacionados com esse registo com uma relação muitos-para-um, registos criados num passo anterior ou valores que fazem parte do próprio processo.  
  
## <a name="next-steps"></a>Próximos passos  
 [Invocar ações personalizadas de um fluxo de trabalho](invoke-custom-actions-workflow-dialog.md)   

 
 
