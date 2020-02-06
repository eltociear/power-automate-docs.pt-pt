---
title: Fluxos de trabalho clássicos do Common Data Service | MicrosoftDocs
ms.custom: ''
ms.date: 08/27/2019
ms.reviewer: matp
ms.service: flow
ms.topic: article
ms.assetid: 1f3c9780-26ad-49ec-a3fb-fc226def19c5
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2bb689f9dff55e8313a22d89efd8fa76eca4fb50
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74369715"
---
# <a name="classic-common-data-service-workflows"></a>Fluxos de trabalho clássicos do Common Data Service 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Os fluxos de trabalho automatizam processos empresariais sem ser necessária uma interface de utilizador. As pessoas costumam utilizar processos de fluxo de trabalho para iniciar automatizações que não exijam qualquer interação por parte do utilizador.

> [!IMPORTANT]
> Utilize fluxos em vez de fluxos de trabalho clássicos para automatizar os processos de negócio. Mais informações: [Substituir os fluxos de trabalho clássicos do Common Data Service por fluxos](replace-workflows-with-flows.md)  
  
 Cada processo de fluxo de trabalho está associado a uma única entidade. Quando configurar fluxos de trabalho, tem de ter em conta quatro áreas principais:  
  
-   Quando devem iniciar?  
  
-   Devem ser executados sob a forma de fluxo de trabalho em tempo real ou em segundo plano?  
  
-   Que ações devem realizar?  
  
-   Sob que condições é que as ações devem ser realizadas?  
  
 Este tópico faz uma introdução sobre como localizar processos de fluxo de trabalho e descreverá quando se devem iniciar estes processos, bem como se estes devem ser executados sob a forma de fluxos de trabalho em tempo real ou em segundo plano. Para obter informações sobre as ações que os fluxos de trabalho devem realizar e sob que condições, veja [Configuring Workflow Processes](configure-workflow-steps.md) (Configurar Processos de Fluxo de Trabalho).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>Onde se personalizam os processos de fluxo de trabalho?  
 Para ver os fluxos de trabalho na sua organização, veja o nó **Processos** na **Solução Predefinida** e filtre os processos que tenham a **Categoria** **Fluxo de Trabalho**.  
  
 ![Processos filtrados por fluxo de trabalho no Dynamics 365](media/workflow-processes-filtered.PNG "Processos filtrados por fluxo de trabalho no Dynamics 365")  
  
 Dependendo da forma como a aplicação é criada, os utilizadores podem criar ou modificar os respetivos fluxos de trabalho na aplicação. 
 
Os programadores podem criar fluxos de trabalho através das informações presentes no [Common Data Service Developer Guide](https://docs.microsoft.com/powerapps/developer/common-data-service/workflow/workflow-extensions) (Guia do Programador do Common Data Service) e as soluções que comprar poderão incluir fluxos de trabalho que poderá modificar.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Propriedades de fluxos de trabalho  
 No explorador de soluções, selecione **Processos** e clique em **Novo**.  
  
 Quando criar um fluxo de trabalho, a caixa de diálogo **Criar Processo** exige a definição de três propriedades que todos os processos contêm:  
  
 ![Criar um fluxo de trabalho no Dynamics 365](media/create-workflow.PNG "Criar um fluxo de trabalho no Dynamics 365")  
  
 **Nome do Processo**  
 O nome do processo de fluxo de trabalho não tem de ser exclusivo, mas se estiver a prever que vai ter muitos fluxos de trabalho, é recomendado utilizar uma convenção de nomenclatura para diferenciar claramente os seus processos. É recomendado aplicar prefixos padrão ao nome do fluxo de trabalho. O prefixo poderá descrever a função do fluxo de trabalho ou o departamento da empresa. Isto vai ajudá-lo a agrupar itens semelhantes na lista de fluxos de trabalho.  
  
 **Categoria**  
 Esta propriedade determina que se trata de um processo de fluxo de trabalho.  
  
 **Entidade**  
 Cada processo de fluxo de trabalho tem de ser definido para uma única entidade. Não é possível alterar a entidade após a criação do processo de fluxo de trabalho.  
  
 **Executar este fluxo de trabalho em segundo plano (recomendado)**  
 Esta opção é apresentada quando seleciona o fluxo de trabalho como a categoria. Esta definição determina se o fluxo de trabalho é um fluxo de trabalho em tempo real ou em segundo plano. A execução dos fluxos de trabalho em tempo real é imediata (síncrona) e a execução dos fluxos de trabalho em segundo plano é assíncrona. As opções de configuração disponíveis variam consoante o tipo de execução que selecionar. Os fluxos de trabalho em segundo plano permitem condições de espera que não estão disponíveis no caso dos fluxos de trabalho em tempo real. Desde que não utilize essas condições de espera posteriormente, pode converter fluxos de trabalho em segundo plano em fluxos de trabalho em tempo real e vice-versa. Para obter mais informações sobre as condições de espera, veja [Setting conditions for workflow actions](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions) (Definir condições para ações de fluxo de trabalho).  
  
 Também tem a opção **Tipo** para especificar se quer criar um novo fluxo de trabalho a partir do zero ou se prefere começar a partir de um modelo existente. Se selecionar **Novo processo baseado num modelo existente (selecione na lista)** , pode escolher um dos processos de Fluxo de Trabalho disponíveis que foram anteriormente guardados como modelo de processo.  
  
 Depois de criar o Fluxo de Trabalho ou de editar um já existente, terá as propriedades adicionais que se seguem:  
  
 ![Separador Geral num fluxo de trabalho](media/create-workflow-general-tab.PNG "Separador Geral num fluxo de trabalho")  
  
 **Ativar Como**  
 Pode selecionar **Modelo de processo** para criar um ponto de partida avançado para outros modelos. Se selecionar esta opção, a mesma não será aplicada após ativar o fluxo de trabalho, mas estará disponível para ser selecionada na caixa de diálogo **Criar Processo** se selecionar **Tipo**: **Novo processo baseado num modelo existente (selecione na lista)**  
  
 Os modelos de processo são úteis se tiver vários processos de fluxo de trabalho semelhantes e os quiser definir sem ter de duplicar a mesma lógica.  
  
> [!NOTE]
>  A edição de modelos de processo não altera os comportamentos dos outros processos de fluxo de trabalho criados anteriormente que os tenham utilizado como modelo. Os novos fluxos de trabalho que forem criados a partir de modelos são uma cópia do conteúdo desses modelos.  
  
 **Disponível para Execução**  
 Esta secção contém opções que descrevem como o fluxo de trabalho está disponível para ser executado.  
  
 **Executar este Fluxo de Trabalho em segundo plano (recomendado)**  
 Esta caixa de verificação reflete a opção que selecionou quando criou o fluxo de trabalho. Esta opção está desativada, mas pode alterá-la a partir do menu **Ações** ao selecionar **Converter num fluxo de trabalho em tempo real** ou **Converter num fluxo de trabalho em segundo plano**.  
  
 **Como processo a pedido**  
 Selecione esta opção se quiser permitir que os utilizadores executem este fluxo de trabalho a partir do comando **Executar Fluxo de Trabalho**.  
  
 **Como um processo subordinado**  
 Selecione esta opção se quiser permitir que o fluxo de trabalho esteja disponível para ser iniciado a partir de outro fluxo de trabalho.  
  
 **Retenção de Tarefas de Fluxo de Trabalho**  
 Esta secção contém uma opção que permite eliminar um fluxo de trabalho após a conclusão da execução do fluxo de trabalho.  
  
 **Eliminar automaticamente as tarefas de fluxo de trabalho concluídas (para poupar espaço em disco)**  
 Selecione esta opção se quiser eliminar automaticamente uma tarefa de fluxo de trabalho.  
  
> [!NOTE]
>  As tarefas de fluxo de trabalho não são eliminadas imediatamente após a conclusão, mas sim pouco tempo depois através de um processo em lotes.  
  
 **Âmbito**  
 No caso das entidades que são propriedade de um utilizador, as opções são **Organização**, **Nível Principal: Unidades de Negócio Subordinadas**, **Unidade de Negócio** ou **Utilizador**. No caso das entidades que são propriedade da organização, a única opção é **Organização**.  
  
 Se o âmbito for **Organização**, a lógica do fluxo de trabalho pode ser aplicada a qualquer registo na organização. Caso contrário, o fluxo de trabalho só pode ser aplicado a um subconjunto de registos que estão dentro do âmbito.  
  
> [!NOTE]
>  O valor predefinido do âmbito é **Utilizador**. Certifique-se de que verifica se o valor do âmbito é o adequado antes de ativar o fluxo de trabalho.  
  
 **Iniciar quando**  
 Utilize as opções nesta secção para especificar o momento em que um fluxo de trabalho deve iniciar automaticamente. Pode configurar um fluxo de trabalho em tempo real para que este seja executado antes de determinados eventos. Esta é uma funcionalidade muito poderosa porque o fluxo de trabalho pode parar a ação antes de ela ocorrer. Mais informações: [Utilizar Fluxos de Trabalho em Tempo Real](configure-workflow-steps.md#BKMK_SynchronousWorkflows). As opções são:  
  
- **O registo foi criado**  
  
- **Registar alterações de estado**  
  
- **O registo foi atribuído**  
  
- **Registar alteração de campos**  
  
- **O registo foi eliminado**  
  
> [!NOTE]
>  Tenha em atenção que as ações e condições que definir para o fluxo de trabalho não conseguem identificar quando é que o fluxo de trabalho é executado. Por exemplo, se definir um fluxo de trabalho para atualizar o registo, esta ação não pode ser realizada por um fluxo de trabalho em tempo real antes da criação do registo. Não é possível atualizar um registo que não existe. Da mesma forma, um fluxo de trabalho em segundo plano não pode atualizar um registo que tenha sido eliminado, ainda que possa definir esta ação para o fluxo de trabalho. Se configurar um fluxo de trabalho para realizar uma ação que não pode ser realizada, a ação e o todo o fluxo de trabalho falharão.  
  
 **Executar Como**  
 Esta opção só está disponível se tiver anulado a seleção da opção **Executar este fluxo de trabalho em segundo plano (recomendado)** quando criou o fluxo de trabalho ou se tiver convertido posteriormente um fluxo de trabalho em segundo plano num fluxo de trabalho em tempo real.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Contexto de segurança dos processos de fluxo de trabalho  
 Quando um fluxo de trabalho em segundo plano está configurado como um processo a pedido e é iniciado por um utilizador através do comando **Executar Fluxo de Trabalho**, as ações que o fluxo de trabalho pode realizar estão limitadas às que o utilizador poderia realizar com base nos privilégios e níveis de acesso definidos pelas funções de segurança definidas para a conta de utilizador do mesmo.  
  
 Quando um fluxo de trabalho em segundo plano é iniciado com base num evento, o fluxo de trabalho opera no contexto da pessoa que é proprietária do mesmo (normalmente, trata-se da pessoa que criou o fluxo de trabalho).  
  
 No caso dos fluxos de trabalho em tempo real, tem a opção **Executar Como** e pode escolher se o fluxo de trabalho deve aplicar o contexto de segurança do proprietário do fluxo de trabalho ou do utilizador que efetuou alterações no registo. Se o seu fluxo de trabalho incluir ações que nenhum utilizador conseguiria realizar devido a restrições de segurança, deve optar por executar o fluxo de trabalho na qualidade de proprietário do fluxo de trabalho.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Ativar um fluxo de trabalho  
 Só é possível editar fluxos de trabalho enquanto estes estiverem desativados. É necessário ativar os fluxos de trabalho antes de estes poderem ser utilizados manualmente ou ser aplicados devido a eventos. Para um fluxo de trabalho poder ser ativado, este tem de conter, pelo menos, um passo. Para obter informações sobre a configuração de passos, veja [Configuring workflow processes](configure-workflow-steps.md) (Configurar processos de fluxo de trabalho).  
  
 Os fluxos de trabalho só podem ser ativados ou desativados pelo proprietário do fluxo de trabalho ou por alguém que tenha o privilégio **Atuar em Nome de Outro Utilizador**, tal como o administrador de sistema.  Isto tem como objetivo impedir que um utilizador mal-intencionado consiga modificar o fluxo de trabalho de alguém sem que essa pessoa se aperceba da alteração. Pode reatribuir um fluxo de trabalho do qual é proprietário ao alterar o proprietário. Este campo encontra-se no separador **administração**. Se não for o administrador de sistema e precisar de editar um fluxo de trabalho que é propriedade de outro utilizador, tem de pedir a esse utilizador para o desativar e para lhe atribuir esse fluxo. Depois de concluir a edição do fluxo de trabalho, pode voltar a atribuí-lo a esse utilizador para que este possa ativar o fluxo.  
  
 Os fluxos de trabalho em tempo real exigem que o utilizador tenha o privilégio **Ativar Processos em Tempo Real**. Como os fluxos de trabalho em tempo real têm uma maior probabilidade de afetar o desempenho do sistema, só as pessoas que conseguem avaliar o risco potencial devem receber este privilégio.  
  
 Os fluxos de trabalho são guardados quando são ativados, pelo que não é necessário guardá-los antes de os ativar.  
  
## <a name="next-steps"></a>Próximos passos  
 [Configuring workflow processes](configure-workflow-steps.md) (Configurar processos de fluxo de trabalho)  <br/>
[Adicionar um fluxo de trabalho a pedido a um fluxo de processo de negócio](bpf-add-on-demand-workflow.md) 

