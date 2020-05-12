---
title: Criar um fluxo do processo de negócio no Power Apps | MicrosoftDocs
description: Saiba como criar um fluxo de processo de negócio
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ad075ec6c4b00d46f000b86aaa9166e40adda640
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296862"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Tutorial: criar um fluxo de processo de negócio para normalizar processos


Este tutorial mostra-lhe como criar um fluxo do processo de negócio com o Power Apps. Para saber mais sobre por que motivo os fluxos de processo de negócio são utilizados, veja [Business process flows overview](business-process-flows-overview.md) (Descrição geral de fluxos de processo de negócio). Para obter informações sobre como criar um fluxo de tarefas móvel, consulte [Criar um fluxo de tarefas móvel](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Quando um utilizador inicia um fluxo de processo de negócio, as fases e os passos do processo são apresentados na barra de processo na parte superior de um formulário:  
  
 ![Processo de negócio com fases](media/business-process-stages.png "Processo de negócio com fases")  
  
 > [!TIP]
 >  Depois de criar uma definição do fluxo de processo de negócio, pode controlar quem pode criar, ler, atualizar ou eliminar a instância do fluxo de processo de negócio. Por exemplo, nos processos relacionados com o suporte, poderá fornecer acesso total aos representantes de suporte ao cliente para alterarem a instância de fluxo do processo de negócio, mas fornecer acesso só de leitura para a instância para representantes de vendas, para que possam monitorizar atividades de pós-vendas para os clientes. Para definir a segurança de uma definição de fluxo do processo de negócio que criou, selecione **Ativar Direitos de Acesso** na barra de ação.  
  
<a name="BKMK_Createbusinessprocessflows"></a>

## <a name="prerequisites"></a>Pré-requisitos

Precisa do [Plano do Flow 2](https://preview.flow.microsoft.com/pricing/) para criar fluxos de processos empresariais. Alguns planos de licença do Dynamics 365 incluem o Plano do Flow 2.

## <a name="create-a-business-process-flow"></a>Criar um fluxo do processo de negócio  
  
1. Abra o [explorador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
  
2. No painel de navegação esquerdo, selecione **Processos**. 
  
3.  Na barra de ferramentas **Ações**, selecione **Novo**.  
  
4.  Na caixa de diálogo **Criar Processo**, preencha os campos obrigatórios:  
  
    -   Introduza um nome de processo. O nome do processo não tem de ser exclusivo, mas tem de ser significativo para os utilizadores que necessitam de selecionar um processo. Pode alterar isto mais tarde.  
  
    -   Na lista **Categoria**, selecione **Fluxo do Processo de Negócio**.  
  
         Não é possível alterar a categoria depois de criar o processo.  
  
    -   Na lista **Entidade**, selecione a entidade em que pretende basear o processo.  
  
         A entidade que selecionar afeta os campos disponíveis para os passos que podem ser adicionados à primeira fase do fluxo do processo. Se não encontrar a entidade pretendida, certifique-se de que a entidade tem a opção Fluxos de processo de negócio (serão criados campos) definida na definição da entidade. Não pode anular esta ação depois de guardar o processo.  
  
5. Selecione **OK**.  
  
     O novo processo é criado e o estruturador do fluxo de processo de negócio é aberto com uma única fase criada automaticamente.  
  
 ![Janela do fluxo do processo de negócio a mostrar os elementos principais](media/business-process-flow-window-showing-main-elements.png "Janela do fluxo do processo de negócio a mostrar os elementos principais")  
  
6. **Adicione fases.** Se os utilizadores avançarem de uma fase de negócio para outra no processo:  
  
    1.  Arraste o componente **Fase** do separador **Componentes**  e largue-o sobre um sinal de + no estruturador.  
  
        ![Arrastar uma fase do processo de negócio](media/drag-business-process-stage.png "Arrastar uma fase do processo de negócio")  
  
    2.  Para definir as propriedades para uma fase, selecione a fase e, em seguida, defina as propriedades no separador **Propriedades** no lado direito do ecrã:  
  
        -   Introduza um nome a apresentar.  
  
        -   Se pretender, selecione uma categoria para a fase.  A categoria (como **Qualificar** ou **Desenvolver**) aparece como divisas na barra de processo.  
  
            ![Divisa da barra do processo de negócio](media/business-process-bar-chevron.png "Divisa da barra do processo de negócio")  
  
        -   Quando tiver terminado de alterar as propriedades, selecione o botão **Aplicar**.  
  
7. **Adicione passos a uma fase.** Para ver os passos numa fase, selecione **Detalhes** no canto inferior direito da fase. Para adicionar mais passos:  
  
    1.  Arraste o componente **Passo** para a fase a partir do separador **Componentes**.  
  
        ![Adicionar um passo a uma fase num processo de negócio](media/add-step-stage-business-process.png "Adicionar um passo a uma fase num processo de negócio")  
  
    2.  Selecione o passo e, em seguida, defina as propriedades no separador **Propriedades**:  
  
        1.  Introduza um nome a apresentar para o passo.  
  
        2.  Se pretender que os utilizadores introduzam dados para concluir um passo, selecione o campo apropriado na lista pendente.  
  
        3.  Selecione **Obrigatório** se os utilizadores tiverem de preencher o campo para concluir o passo antes de avançar para a fase seguinte do processo.  
  
        4.  Selecione **Aplicar** quando terminar.  
  
8. **Adicionar um ramo (condição) ao processo.** Para adicionar uma condição de ramificação:  
  
    1.  Arraste o componente **Condição** do separador **componentes** para um sinal de + entre duas fases.  
  
        ![Adicionar uma Condição a um fluxo do processo de negócio](media/add-condition-business-process-flow.png "Adicionar uma Condição a um fluxo de processo de negócio")  
  
    2.  Selecione a condição e, em seguida, defina as propriedades no separador **Propriedades**. Para mais informações sobre as propriedades de ramificação, consulte [Melhorar fluxos de processos de negócio através de ramificação](enhance-business-process-flows-branching.md). Quando tiver terminado de definir as propriedades para a condição, selecione **Aplicar**.  
  
9. **Adicionar um fluxo de trabalho.** Para chamar um fluxo de trabalho:  
  
    1.  Arraste um componente **Fluxo de Trabalho** do separador **Componentes** para uma base ou para o item **Fluxo de Trabalho Global** no estruturador.   O item que adicionar a este depende do seguinte:  
  
       - **Arraste-o para uma fase** quando pretender acionar o fluxo de trabalho à entrada ou saída da fase. O componente de fluxo de trabalho tem de ser baseado na mesma entidade primária que a fase.  
  
       - **Arraste-o para o item de Fluxo de Trabalho Global** quando pretende acionar o fluxo de trabalho quando o processo é ativado ou quando o processo é arquivado (quando o estado é alterado para **Concluído** ou **Abandonado**). O componente de fluxo de trabalho tem de ser baseado na mesma entidade primária que o processo.  
  
    2.  Selecione o fluxo de trabalho e, em seguida, defina as propriedades no separador **Propriedades**:  
  
       1.  Introduza um nome a apresentar.  
  
       2.  Selecione quando o fluxo de trabalho deve ser acionado.  
  
       3.  Procure um fluxo de trabalho ativo a pedido existente que corresponda à entidade fase ou crie um novo fluxo de trabalho ao selecionar **Novo**.  
  
       4.  Selecione **Aplicar** quando terminar.  
  
       Para mais informações sobre fluxos de trabalho, consulte [Processos de fluxo de trabalho](../common-data-service/workflow-processes.md).  
  
10. Para validar o fluxo do processo de negócio, selecione **Validar** na barra de ação.  
  
11. Para guardar o processo como rascunho enquanto continuar a trabalhar no mesmo, selecione **Guardar** na barra de ação.  
  
    > [!IMPORTANT]
    >  Como um processo é um rascunho, os utilizadores não vão conseguir utilizá-lo.  
  
12. Para ativar o processo e disponibilizá-lo a sua equipa, selecione **Ativar** na barra de ação.  

13. Para fornecer controlo sobre quem pode criar, ler, atualizar ou eliminar a instância de fluxo do processo de negócio, selecione **Editar Direitos de Acesso** na barra de comandos do estruturador. Por exemplo, nos processos relacionados com o suporte, poderá fornecer acesso total aos representantes de suporte ao cliente para alterarem a instância de fluxo do processo de negócio, mas fornecer acesso só de leitura para a instância para representantes de vendas, para que possam monitorizar atividades de pós-vendas para os clientes.

  No ecrã **Direitos de Acesso**, selecione o nome de um direito para abrir a página de informações de direito de acesso. Selecione o separador Fluxos de Processo de Negócio e, em seguida, atribua os privilégios apropriados no fluxo do processo de negócio para um direito de acesso.

  > [!NOTE]
  > Por predefinição, as funções Administrador de Sistema e Personalizador de Sistemas têm acesso aos novos fluxos de processo de negócio.

   ![Atribuir privilégios a um fluxo do processo de negócio](media/bpf-assign-privileges.png)

  Especifique os privilégios ao selecionar os botões de opção apropriados e, em seguida, clique em Guardar. Para mais informações acerca de privilégios, consulte [Privilégios do fluxo do processo de negócio](business-process-flows-overview.md#BKMK_MultipleBPF).

  Em seguida, não se esqueça de atribuir o direito de acesso a utilizadores apropriados na sua organização.

> [!TIP] 
>  Eis algumas sugestões para ter em consideração enquanto trabalha no seu fluxo de tarefas na janela do estruturador:  
>   
> - Para criar um instantâneo de tudo na janela do fluxo do processo de negócio, selecione **Instantâneo** na barra de ação. Isto é útil, por exemplo, se pretender partilhar e obter comentários sobre o processo de um membro da equipa.  
> - Utilize o minimapa para navegar rapidamente para várias partes do processo. Isto é útil quando tiver um processo complicado que ocupa uma área superior à disponibilizada pelo ecrã.  
> - Para adicionar uma descrição para o processo de negócio, selecione **Detalhes** sob o nome de processo no canto superior esquerdo da janela de fluxo do processo de negócio. Pode utilizar até 2000 caracteres.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Editar um fluxo do processo de negócio  
 Para editar os fluxos do processo de negócio, abra o explorador de soluções, selecione **Processos** e selecione o **Fluxo do Processo de Negócio** a partir da lista de processos que pretende editar.  
  
 Quando seleciona o nome do fluxo do processo de negócio que pretende editar a partir da lista de processos, é aberto no estruturador, onde pode efetuar as atualizações que pretende. Expanda **Detalhes** no nome do processo para lhe mudar o nome ou adicionar uma descrição e ver informações adicionais.  
  
 ![Secção de detalhes expandida de um fluxo de processo de negócio](media/business-process-flow-details.png "Secção de detalhes expandida de um fluxo de processo de negócio")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Outros aspetos a saber sobre os fluxos de processo de negócio
 **Editar fases**  
Os fluxos de processos empresariais podem ter até 30 fases.    
  
Pode adicionar ou alterar as propriedades seguintes de uma fase:  
  
- **Nome da Fase**  
  
- **Entidade**. Pode alterar a entidade para qualquer fase exceto a primeira.  
  
- **Categoria da Fase**. Uma categoria permite agrupar fases por um tipo de ação. É útil para relatórios que agruparão registos pela fase em que se encontram. As opções para a categoria da fase provêm do conjunto de opções global Categoria da Fase. Pode adicionar opções adicionais para este conjunto de opções global e altere as etiquetas de opções existentes se pretender. Também pode eliminar estas opções se quiser, mas recomendamos que mantém as opções existentes. Não poderá adicionar a correspondência da mesma anterior a opção se eliminar. Se não pretender utilizar, altere a etiqueta “não utilizam”.  
  
- **Relação**. Introduza uma relação quando a fase anterior no processo é baseada noutra entidade. Para a fase atualmente a ser definida, selecione **Selecionar relações** para identificar uma relação a utilizar quando mover entre as duas fases. Recomendamos que selecione uma relação para desfrutar das vantagens seguintes:  
  
    -   As relações têm frequentemente mapas de atributos definidos que transportam automaticamente os dados entre registos, minimizando a introdução de dados.  
  
    -   Quando seleciona **Fase Seguinte** na barra de processo de um registo, todos os registos que utilizem a relação são listados no fluxo do processo, fomentando consequentemente a reutilização de registos do processo. Além disso, pode utilizar fluxos de trabalho para automatizar a criação de registos de modo a que o utilizador só tenha de selecionar em vez de criar, para otimizar o processo.  
  
**Passos de Edição**  
 Cada fase pode ter até 30 passos.    
  
**Adicionar ramo**  
Para obter informações sobre como adicionar um ramo a uma fase, consulte [Melhorar fluxos do processo de negócio com ramificação](enhance-business-process-flows-branching.md).  
  
Para criar um fluxo de processos de negócio disponível para pessoas com a utilização, terá de pedir ao fluxo de processo, permite direitos de acesso e, ativa-os.  
  
**Definir Ordem do Fluxo do Processo**  
 Se tiver mais de um fluxo de processo de negócio para uma entidade (tipo de registo), terá de definir o processo que é atribuído automaticamente aos novos registos. Na barra de comandos, selecione **Ordenar Fluxo do Processo**. No caso de novos registos ou registos que ainda não têm um fluxo de processo associado a eles, será utilizado o primeiro fluxo de processo de negócio a que um utilizador tem acesso.  
  
**Ativar Direitos de Acesso**  
Os utilizadores têm acesso a um fluxo de processo de negócio consoante o privilégio definido no fluxo de processo de negócio na função de segurança atribuída ao utilizador. 

Por predefinição, os direitos de acesso só de **Administrador de sistema** e de **Personalizador de sistema** podem ver um novo fluxo de processos de negócio. 

Para especificar os privilégios num fluxo de processo de negócios, abra o fluxo de processo de negócios para edição e, em seguida, selecione **Editar Funções de Segurança** na barra de comando do estruturador do fluxo de processo de negócio. Veja o passo 13 em [Criar um fluxo de processo de negócio](#create-a-business-process-flow) listado no início deste tópico.
  
**Activar**  
Tem de ativar o fluxo de processo de negócio antes de qualquer pessoa o poder utilizar. Na barra de comandos, selecione **Ativar**. Depois de confirmar ativação, o fluxo de processos de negócio está pronto a utilizar. Se um fluxo de processo de negócio tiver erros, só poderá ativá-lo depois de corrigir os erros.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Adicionar uma ação a pedido a um fluxo de processo de negócio
A atualização do Dynamics 365 (online) versão 9.0 introduz uma funcionalidade do fluxo do processo de negócio: automatização do fluxo do processo de negócio com os Passos da Ação. Poderá adicionar um botão a um fluxo do processo de negócio que irá acionar uma ação ou um fluxo de trabalho.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Adicionar fluxos de trabalho a pedido ou ações utilizando um Passo de Ação
Suponha que, como parte do processo de qualificação de oportunidades, a organização Contoso exige que todas as oportunidades sejam revistas por um revisor designado. Em seguida, a organização Contoso criou uma ação que: 

- Cria um registo de tarefa que é atribuído ao revisor da oportunidade. 
- Anexa “Pronto para Revisão” ao tópico da oportunidade. 

Além disso, a Contoso tem de ser capaz de executar estas ações a pedido. Para integrar estas tarefas no processo de qualificação de oportunidades, as ações têm de ser apresentadas no fluxo do processo da oportunidade de negócio. Para ativar esta funcionalidade, selecione **Como um passo de ação do Fluxo do Processo de Negócio**.
![Disponível para execução como um fluxo do processo de negócio.](media/action-available-to-run.png)

Em seguida, o Passo da Ação é adicionado ao fluxo do processo de negócio da oportunidade da Contoso. Em seguida, o fluxo do processo é validado e atualizado.

![Ação adicionada ao Fluxo do Processo de Negócio da oportunidade.](media/add-action-to-bpf.png)

Agora, os membros da força de vendas da Contoso pode iniciar a ação a partir do passo do processo de negócio **Qualificação da Oportunidade**, a pedido, selecionando **Executar**.

![Execute a ação.](media/action-execute.png)

> [!IMPORTANT]
> - Para conseguir executar uma ação ou fluxo de trabalho a pedido, o fluxo do processo de negócio tem de incluir um Passo da Ação. Se o Passo da Ação executar um fluxo de trabalho, o fluxo de trabalho terá de ser configurado para ser executado a pedido.
> - A entidade associada à ação ou ao fluxo de trabalho tem de ser a mesma entidade associada ao fluxo do processo de negócio.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Limitação à utilização dos Passos da Ação num fluxo do processo de negócio

- As ações do não estão disponíveis como Passos da Ação se os parâmetros de entrada ou saída forem do tipo Entity, EntityCollection ou OptionSet (Picklist). As ações com mais de um parâmetro de saída EntityReference ou qualquer número de parâmetros de entrada EntityReference não estão disponíveis como Passos da Ação. As ações não associadas a uma entidade principal (ação global) não estão disponíveis como Passos de Ação.

## <a name="instant-flows-in-business-process-flows"></a>Fluxos instantâneos em fluxos de processo de negócio

Pode executar um **fluxo instantâneo** para automatizar tarefas repetitivas, gerar documentos, controlar aprovações e muito mais a partir de uma fase num processo de negócio.

### <a name="add-an-instant-flow-as-a-step-in-a-business-process"></a>Adicionar um fluxo instantâneo como um passo num processo de negócio

Suponhamos que vende impressoras e que utiliza o **Processo de Vendas da Oportunidade Potencial** para fechar as negociações. Como parte deste processo, gostaria que o líder de equipa analisasse e aprovasse as propostas que a equipa de vendas prepara numa fase anterior do fluxo do processo de negócio antes de as partilhar com o cliente.

Para isso, precisa de fazer duas coisas:
1. Criar um fluxo instantâneo que solicite a análise e aprovação da proposta por parte da equipa.
1. Adicionar o fluxo instantâneo como um passo no **Processo de Vendas da Oportunidade Potencial**.

> [!TIP]
> Apenas os [fluxos com suporte para soluções](https://docs.microsoft.com/flow/overview-solution-flows) podem ser adicionados como um passo num processo de negócio. 

### <a name="build-an-instant-flow"></a>Criar um fluxo instantâneo

1. No Power Automate, selecione **Soluções** no menu de navegação.
1. Selecione **Solução Predefinida** na lista de soluções apresentada. 
1. Selecione o menu **+ Novo** e, em seguida, **Fluxo** na lista apresentada.
1. Procure e, em seguida, selecione o conector do **Common Data Service**.
1. Procure e selecione o acionador **Quando um registo é selecionado** na lista de acionadores do **Common Data Service**.
1. Defina o **Ambiente** como **Predefinido** e, em seguida, defina o **Nome da Entidade** como **Processo de Vendas da Oportunidade Potencial**.
1. Adicione um campo de texto para o utilizador introduzir a ligação para a proposta.

   ![Acionador de fluxo instantâneo](media/instant-flow-trigger.png "Acionador de fluxo instantâneo")

   Vamos precisar de informações relativas à instância do fluxo do processo de negócio para ajudar a fornecer contexto para o pedido de aprovação. Para tal, siga estes passos.

1. Adicione a ação **Analisar JSON**. 
1. Defina **Conteúdo** como **entidade** ao selecionar na lista de valores dinâmicos do acionador **Quando um registo é selecionado**.
1. Cole o seguinte conteúdo no campo **Esquema**.

    ```json
    {
        "type": "object",
        "properties": {
        "entity": {
            "type": "object",
            "properties": {
                "FlowsWorkflowLogId": {
                    "type": "string"
                },
                "BPFInstanceId": {
                    "type": "string"
                },
                "BPFInstanceEntityName": {
                    "type": "string"
                },
                "BPFDefinitionId": {
                    "type": "string"
                },
                "BPFDefinitionEntityName": {
                    "type": "string"
                },
                "StepId": {
                    "type": "string"
                },
                "BPFDefinitionName": {
                    "type": "string"
                },
                "BPFInstanceName": {
                    "type": "string"
                },
                "BPFFlowStageLocalizedName": {
                    "type": "string"
                },
                "BPFFlowStageEntityName": {
                    "type": "string"
                },
                "BPFFlowStageEntityCollectionName": {
                    "type": "string"
                },
                "BPFFlowStageEntityRecordId": {
                    "type": "string"
                },
                "BPFActiveStageId": {
                    "type": "string"
                },
                "BPFActiveStageEntityName": {
                    "type": "string"
                },
                "BPFActiveStageLocalizedName": {
                    "type": "string"
                }
            }
          }
        }
   }
   ```

   Neste momento, deverá ter o seguinte aspeto:

   ![Analisar JSON](media/instant-flow-json-date.png "Analisar JSON")

  1. Adicione a ação **Obter registo** a partir do conector do **Common Data Service**.
  1. Defina **Ambiente** como **(Atual)**, **Nome da Entidade** como **Processo de Vendas da Oportunidade Potencial** e **Identificador de Item** como **BPFFlowStageEntityRecordID**.

     ![Adicionar um registo](media/instant-flow-add-record.png)

     Agora que temos os dados, defina o processo de aprovação. Para tal, adicione a ação **Iniciar e aguardar uma aprovação (V2)** e preencha as informações relevantes. Saiba mais acerca das [aprovações]( sequential-modern-approvals.md) se não estiver familiarizado.

     > [!TIP]
     > - Utilize o seletor de conteúdo dinâmico para adicionar campos da ação **Obter registo** para adicionar informações relevantes ao pedido de aprovação, de forma a que os aprovadores possam perceber facilmente do que se trata. 
     > - Para fornecer mais contexto relativamente à fase ativa em que se encontra o processo de negócio, adicione o campo **BPFActiveStageLocalizedName** na lista de valores dinâmicos.

     O cartão **Iniciar e guardar uma aprovação (V2)** poderá ter um aspeto semelhante a este:

      ![Cartão de aprovação](media/instant-flow-add-approval-action.png)

1. Por fim, guarde o fluxo e ative-o.

### <a name="add-this-flow-as-a-step-in-the-lead-to-opportunity-sales-process"></a>Adicionar este fluxo como um passo no Processo de Vendas da Oportunidade Potencial

Agora que criou o fluxo instantâneo, só precisa de o adicionar ao fluxo do processo de negócio. 

1. Abra o **Processo de Vendas da Oportunidade Potencial** no estruturador de fluxos de processos de negócio. 
1. Arraste e largue o **Passo do Fluxo (Pré-visualização)** da lista de **Componentes** na fase **Propor**.
1. Em seguida, selecione o ícone de pesquisa no campo **Selecionar um Fluxo** para listar todos os fluxos que pode adicionar a um fluxo de processo de negócio.
1. Selecione um fluxo na lista e, em seguida, guarde as alterações ao selecionar o botão **Aplicar** na parte inferior do painel das propriedades.
1. Por fim, selecione o botão **Atualizar** para disponibilizar aos utilizadores este fluxo de processo de negócio com o novo passo de fluxo instantâneo.


## <a name="the-action-center"></a>O centro de ações

Quando precisar de ver a lista de fluxos de processos de negócio em que está envolvido, consulte o centro de ações unificado. 

![Vista de fluxos de processos de negócio do centro de ações unificado](media/approvals-center.png "Vista de fluxos de processos de negócio do centro de ações unificado")

![Vista de fluxos de aprovação do centro de ações unificado](media/action-center-bpf.png "Vista de fluxos de aprovação do centro de ações unificado")

No centro de ações unificado, verá todos os processos de negócio nos quais lhe está atribuído, pelo menos, um registo de entidade do Common Data Service que o processo utiliza. Por exemplo, se um processo do negócio utilizar as entidades **Oportunidade potencial** e **Oportunidade** no Common Data Service, verá todas as instâncias deste processo onde o registo de Oportunidade potencial ou de Oportunidade lhe está atribuído.

Ver todas as instâncias que estão a ser trabalhadas no separador **Ativo**. A partir deste separador, pode ver os seguintes detalhes:

- O nome do processo.
- A fase atual de cada processo.
- O proprietário do registo do Common Data Service associado à fase ativa.
- O tempo desde que a instância foi criada.

Para ver

Selecione uma instância para a abrir num separador novo ou selecione-a para copiar uma ligação, partilhar uma ligação por e-mail, abandonar ou eliminar a instância.
  
## <a name="next-steps"></a>Passos seguintes

 - [Descrição geral de fluxos de processos de negócio](business-process-flows-overview.md)  
 - [Melhorar fluxos de processo de negócio com ramificação](enhance-business-process-flows-branching.md)
 - [Descrição geral das aprovações](sequential-modern-approvals.md)
 - [Passos detalhados para adicionar um fluxo instantâneo a um fluxo de processo de negócio](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/instant-steps-business-process-flows)


