---
title: Fluxos de trabalho do Common Data Service clássicos | MicrosoftDocs
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
ms.openlocfilehash: 53bc2b24da55c8700412b527c7f27934e5515bc4
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298336"
---
# <a name="classic-common-data-service-workflows"></a>Fluxos de trabalho do Common Data Service clássicos 


Os fluxos de trabalho automatizam os processos de negócio sem uma interface de utilizador. As pessoas costumam utilizar processos de fluxo de trabalho para iniciar automatizações que não exijam qualquer interação por parte do utilizador.

> [!IMPORTANT]
> Utilize fluxos em vez de fluxos de trabalho clássicos para automatizar os processos de negócio. Mais informações: [Substituir fluxos de trabalho do Common Data Service clássicos por fluxos](replace-workflows-with-flows.md)  
  
 Cada processo de fluxo de trabalho está associado a uma única entidade. Quando configurar fluxos de trabalho, tem de ter em conta quatro áreas principais:  
  
-   Quando começar?  
  
-   Devem ser executado como um fluxo de trabalho em tempo real ou fluxo de trabalho em segundo plano?  
  
-   Que ações que devem executar?  
  
-   Em que condições é que as ações devem ser efetuadas?  
  
 Este tópico explica como localizar processos de fluxo de trabalho e descreve quando os trabalhos começam e se devem ser executados em tempo real ou em segundo plano. Para obter informações sobre as ações que devem efetuar e as condições, consulte [Configurar Processos de Fluxo de Trabalho](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>Pode personalizar processos de fluxo de trabalho?  
 Pode ver os fluxos de trabalho na sua organização vendo o nó **Processos** na **solução predefinida** e filtrando os processos na **categoria** **Fluxo de trabalho**.  
  
 ![Processos filtrados por fluxo de trabalho no Dynamics 365](media/workflow-processes-filtered.PNG "Processos filtrados por fluxo de trabalho no Dynamics 365")  
  
 Dependendo da forma como a aplicação é criada, os utilizadores podem criar ou modificar os respetivos fluxos de trabalho na aplicação. 
 
Os programadores podem criar fluxos de trabalho utilizando as informações no [Guia do Programador do Common Data Service](https://docs.microsoft.com/powerapps/developer/common-data-service/workflow/workflow-extensions) e as soluções que adquirir podem incluir fluxos de trabalho que pode modificar.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Propriedades de fluxo de trabalho  
 No explorador de soluções, em **Processos** selecione e clique em **Novo**.  
  
 Ao criar um fluxo de trabalho do diálogo **Criar processo** necessita de três definir propriedades que têm quaisquer processos:  
  
 ![Criar um fluxo de trabalho no Dynamics 365](media/create-workflow.PNG "Criar um fluxo de trabalho no Dynamics 365")  
  
 **Nome do Processo**  
 O nome do processo de fluxo de trabalho não tem de ser exclusivo, mas se estiver a prever que vai ter muitos fluxos de trabalho, é recomendado utilizar uma convenção de nomenclatura para diferenciar claramente os seus processos. Poderá aplicar prefixos padrão do nome do fluxo de trabalho. O prefixo é descrever a função de fluxo de trabalho ou o departamento da empresa. Isto irá ajudá-lo aos artigos semelhantes na lista de fluxos de trabalho.  
  
 **Categoria**  
 Esta propriedade estabelece que é um processo de fluxo de trabalho.  
  
 **Entidade**  
 Cada processo de fluxo de trabalho tem de ser definido a uma única entidade. Não pode alterar a entidade após o processo de fluxo de trabalho ser criado.  
  
 **Executar este fluxo de trabalho em segundo plano (recomendado)**  
 Esta opção é apresentada quando seleciona o fluxo de trabalho como categoria. Esta definição determina se o fluxo de trabalho é um fluxo de trabalho em tempo real ou em segundo plano. Funciona em tempo real (executados de modo síncrono) e funciona em segundo plano executados de modo assíncrono. As opções de configuração disponíveis dependem à sua escolha para esta definição. Os fluxos de trabalho em segundo plano permitem as condições de espera que não estão disponíveis para fluxos de trabalho em tempo real. à medida que não utiliza as condições de espera, posteriormente pode converter fluxos de trabalho em segundo plano para fluxos de trabalho em tempo real e às de tempo real para funciona em segundo plano. Para mais informações sobre condições de espera, consulte [Definir condições para ações de fluxo de trabalho](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 Também tem a opção de **Tipo** para especificar se criar o zero um novo fluxo de trabalho ou que partir de um modelo existente. Quando escolhe **Novo processo de um modelo existente (selecione na lista)** pode optar por criar relatórios disponíveis fluxos de trabalho que anteriormente como guardar um modelo de processo.  
  
 Depois de criar o Fluxo de Trabalho ou de editar um já existente, terá as propriedades adicionais que se seguem:  
  
 ![Separador Geral num fluxo de trabalho](media/create-workflow-general-tab.PNG "Separador Geral num fluxo de trabalho")  
  
 **Activar Como**  
 Pode optar por criar **Modelo de processo** ponto de partida avançada para outros modelos. Se selecionar esta opção, depois de activá-la o fluxo de trabalho não será aplicado mas isso estará disponível para selecionar no diálogo de **Criar processo** se selecionar **Tipo**: **Novo processo de um modelo existente (selecione na lista)**  
  
 Os modelos de processo são convenientes quando tiver vários processos semelhantes de fluxo de trabalho e pretender definir os sem duplicar a mesma lógica.  
  
> [!NOTE]
>  Editar um modelo de processo não altera os comportamentos de qualquer outro fluxo de trabalho processo criado anteriormente utilizando o como modelo. Um novo fluxo de trabalho criado um modelo é uma cópia do conteúdo no modelo.  
  
 **Disponível para Execução**  
 Esta secção contém as opções que descrevem como o fluxo de trabalho está disponível para ser executado.  
  
 **Executar este fluxo de trabalho em segundo plano (recomendado)**  
 Esta caixa de verificação refletem a opção que selecionou quando criou o fluxo de trabalho. Esta opção está desativada, mas poderá alterá-lo no menu de **Ações** escolher **Converter num fluxo de trabalho em tempo real** ou **Converter num fluxo de trabalho em segundo plano**.  
  
 **Como processo a pedido**  
 Escolha esta opção se pretender permitir que os utilizadores executem este fluxo de trabalho do comando de **Executar fluxo de trabalho**.  
  
 **Como processo subordinado**  
 Escolha esta opção se pretender permitir que funciona está disponível para ser parte dos outros trabalhos.  
  
 **Retenção de Tarefas de Fluxo de Trabalho**  
 Esta secção contém uma opção para eliminar um funciona após a execução de trabalho concluídas.  
  
 **Eliminar automaticamente as tarefas de fluxo de trabalho concluídas (para poupar espaço em disco)**  
 Escolha esta opção, caso pretenda uma tarefa de fluxo de trabalho concluídas podem ser eliminados automaticamente.  
  
> [!NOTE]
>  As tarefas de fluxo de trabalho não são eliminadas da conclusão, mas pouco depois, por um processo de grupo.  
  
 **Âmbito**  
 Para entidades que são propriedade, as opções são **Organização**, **Nível principal: Unidades de negócio subordinadas**, **Unidade de negócio**, ou **Utilizador**. Para entidades que são propriedade da opção está **Organização**.  
  
 Se o âmbito está **Organização**, a lógica de fluxo de trabalho pode ser aplicada a qualquer registo na organização. Caso contrário, o fluxo de trabalho só sejam aplicados a um subconjunto de registos que os ficheiros incidem no âmbito.  
  
> [!NOTE]
>  O valor de âmbito predefinido é **Utilizador**. Certifique-se de que o valor verificar o espaço for apropriado antes de ativar o fluxo de trabalho.  
  
 **Iniciar quando:**  
 Utilize as opções contidas nesta secção para especificar quando um fluxo de trabalho deve iniciar automaticamente. Pode configurar um fluxo de trabalho em tempo real a ser executado antes de determinados eventos. Esta é uma funcionalidade muito poderosa porque o fluxo de trabalho pode parar a ação antes de ela ocorrer. Mais informações: [Using Real-time Workflows](configure-workflow-steps.md#BKMK_SynchronousWorkflows) (Utilizar Fluxos de Trabalho em Tempo Real). As opções são:  
  
- **O registo foi criado**  
  
- **Registar alterações de estado**  
  
- **O registo foi atribuído**  
  
- **Registar alteração de campos**  
  
- **O registo foi eliminado**  
  
> [!NOTE]
>  Tenha em atenção que este ações e condições que define para não funciona em conta do trabalha quando são executados. Por exemplo, se definir um fluxo de trabalho para atualizar o registo, esta ação não pode ser efetuada por um fluxo de trabalho em tempo real para que o registo foi criado. Um registo que não existe não pode ser atualizado. Similarmente, um segundo plano de trabalho não podem atualizar um registo que está a eliminar, embora fosse possível definir esta ação para funciona. Se configurar um funciona para efetuar uma ação que não pode ser efetuada, falha e funciona inteiros irá falhar.  
  
 **Executar como:**  
 Esta opção só está disponível se o unselected a opção de **Execute este fluxo de trabalho em segundo plano (recomendado)** quando criou o trabalha ou se converteu mais tarde um segundo plano de trabalho seja um fluxo de trabalho em tempo real.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Contexto de segurança do processo de fluxo de trabalho  
 Quando um fluxo de trabalho em segundo plano for configurado como um processo a pedido e iniciado por um utilizador que utiliza o comando de **Executar fluxo de trabalho**, as ações que o fluxo de trabalho pode efetuar estão limitadas a que o utilizador poderá executar com base nos privilégios e níveis de acesso em definidos pelo direito de acesso definidos para a sua conta de utilizador.  
  
 Quando o início de um fluxo de trabalho em segundo plano com base num evento estejam em funcionamento num funciona no contexto da pessoa que o proprietário, normalmente pessoa que criou o trabalha.  
  
 Para fluxos de trabalho em tempo real terá a opção de **Executar como** e poderá selecionar se o fluxo de trabalho tem de aplicar o contexto de segurança do proprietário do fluxo de trabalho ou de utilizador que alterações efetuadas ao registo. Se os incluem as ações que todos os utilizadores não podem executar com base em restrições de segurança, tem de especificar que funciona executados como proprietário do fluxo de trabalho.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Ativar um fluxo de trabalho  
 Os fluxos de trabalho podem ser editados apenas quando estão desativados. Antes de um fluxo de trabalho pode ser utilizado manualmente ou foi aplicado devido aos eventos tem de ser ativada. Antes de um fluxo de trabalho pode ser ativado tem de conter pelo menos um passo. Para obter informações sobre passos de configuração, consulte [Configurar processos de fluxo de trabalho](configure-workflow-steps.md)  
  
 Um as relações só podem ser ativado ou desativado por proprietário de trabalho ou por alguém com o privilégio de **Atuar em nome de outro utilizador** como o administrador de sistema.  O motivo para esta é que um utilizador malicioso poderá modificar alguém fluxo de trabalho sem eles que estão em conta de alteração. Pode reatribuir um fluxo de trabalho que possui alterando o proprietário. Este campo está no separador **Administração**. Se não for o administrador de sistema e precisar de editar um fluxo de trabalho que seja propriedade de outro utilizador, precisa de o desativar e atribuí-lo a si próprio. Depois de concluir a edição do fluxo de trabalho, pode atribuí-lo novamente para que possa ser ativado.  
  
 Os fluxos de trabalho em tempo real do utilizador que tem o privilégio de **Ativar processos de tempo real**. Dado que os fluxos de trabalho em tempo real têm um risco de maior afectar o desempenho do sistema, apenas os utilizadores que poderão avaliar os riscos potencial têm de ser dados este privilégio.  
  
 Os fluxos de trabalho são guardados quando são ativados, pelo que não é necessário guardá-los antes de os ativar.  
  
## <a name="next-steps"></a>Passos seguintes  
 [Configuring workflow processes](configure-workflow-steps.md) (Configurar processos de fluxo de trabalho)  <br/>
[Adicionar um fluxo de trabalho a pedido a um fluxo de processo de negócio](bpf-add-on-demand-workflow.md) 

