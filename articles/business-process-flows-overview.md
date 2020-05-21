---
title: Descrição geral dos fluxos do processo de negócio | MicrosoftDocs
ms.custom: ''
ms.date: 12/12/2019
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a6e936b833f6b1e1d6cf6e050031969d41e40de6
ms.sourcegitcommit: 31692af25f91af60cf77572edcb0c986602dc9a6
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/03/2020
ms.locfileid: "3298886"
---
# <a name="business-process-flows-overview"></a>Descrição geral dos fluxos do processo de negócio


Ao criar um processo de negócio, pode ajudar a assegurar que os utilizadores introduzem os dados de maneira consistente e seguem os mesmos passos sempre que trabalham com um cliente. Por exemplo, pode criar um fluxo de processo de negócio em que todos processem os pedidos do suporte ao cliente da mesma forma, ou solicitar aos utilizadores aprovação de uma fatura antes de submeter uma encomenda. Os fluxos de processos de negócio utilizam a mesma tecnologia subjacente que outros processos, mas as capacidades extremamente que fornecem são diferentes das outras funcionalidades que utilize processos. Para obter informações sobre como criar ou editar um fluxo do processo de negócio, consulte [Criar um fluxo do processo de negócio](create-business-process-flow.md).  
  
 [Assista a um pequeno vídeo (4:49) sobre os fluxos do processo de negócio.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Porquê utilizar fluxos de processo de negócio?  
Os fluxos de processos de negócio fornecem um guia para as pessoas que permitem o trabalho efectuado. Fornecnuma experiência de utilizador que otimizada oportunidade potencial pessoas com processos que a organização definiu para as interações que necessitam de ser avançadas a uma fim de qualquer tipo. Esta experiência de utilizador pode ser adaptada para os utilizadores com diferentes direitos de acesso poderem ter uma experiência mais adequada ao trabalho que fazem.  
  
 Utilize fluxos de processos de negócio para definir um conjunto de passos para que os utilizadores sigam para a tomá-los resultado pretendido. Estes passos fornecnuma janela visual que indica as pessoas que estão no processo de negócio. Os fluxos de processos de negócio reduzem a necessidade de formação para os novos utilizadores não têm que afetam toda a organização que entidades têm de utilizar o. Pode informar o processo guiá-los. Pode configurar fluxos de processos de negócio para dar suporte a metodologias de vendas comuns que podem ajudar os grupos de vendas para obter melhores resultados. Para conjuntos de serviço, fluxos de processos empresariais podem ajudar o novo pessoal a mais rapidamente a velocidade acima-à- e a evitar erros que poderão originar aos clientes insatisfeitos.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>O que podem fazer os fluxos do processo de negócio?  
 Com fluxos de processos de negócio, pode definir um conjunto *de fases* e *passos* apresentados num controlo na parte superior do formulário.  
  
 ![Processos de negócio com fases](media/business-process-stages.png "Processo de negócio com fases")  
  
 Cada fase contém um conjunto de passos. Cada passo representa um campo nos dados possam ser introduzidos. Os utilizadores avançam para a fase seguinte utilizando o botão **A fase seguinte**. Pode efetuar um passo de necessária para que os utilizadores deveria introduzir dados para o campo correspondente para poder avançar para a fase seguinte. Isto é denominado fase- bloquear “não”.  
  
 Os fluxos de processos de negócio aparecem relativamente simples que a outros tipos de processo porque não fornecernuma lógica ou condicional automatização de negócio para além de fornecer a experiência otimizada para a introdução de dados e controlar a entrada de dados em fases. Contudo, quando são corresponder a outros processos e personalizações, podem desempenhar um papel importante em tempo de pessoas a guardar, reduzir, custos de formação e aumentar a adoção de utilizador.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Fluxos de processos de negócio integradas com outras personalizações  
 Quando ou o utilizador introduza dados utilizando fluxos de processos de negócio, as alterações são aplicadas de dados também campos de formulário para que todas a automatização fornecida pelas regras de negócio ou por scripts de formulário pode ser aplicado imediatamente. Os passos que é possível adicionar valores definidos para campos que não estiverem presentes no formulário e destes campos serão adicionados ao modelo de objeto `Xrm.Page` utilizado para o formulário scripts. Todos os fluxos de trabalho que são iniciados por alterações aos campos incluídos num fluxo de processos de negócio serão aplicadas quando os dados no formulário guardada. Se a automatização é aplicada por um fluxo de trabalho em tempo real, as alterações serão imediatamente visíveis ao utilizador quando os dados no formulário são atualizados depois de guardar o registo.  
  
 Embora o fluxo de um controlo de processos de negócio no formulário não forneça algumas programmability direto do lado, as alterações aplicadas pelas regras de negócio ou por scripts de formulário são aplicadas automaticamente para controlo do fluxo de um processo de negócio. Se tiver esconde um campo num formulário, o campo poderá também oculto no fluxo de um controlo de processos de negócio. Se definir um valor a utilização de regras de negócio ou scripts de formulário, o valor é definido no fluxo de processos de negócio.  
  
### <a name="concurrent-process-flows"></a>Fluxos do processo simultâneo  
 Os fluxos do processo de negócio simultâneos permitem aos personalizadores configurar vários processos de negócio e associá-los ao mesmo registo inicial. Os utilizadores podem alternar entre vários processos de negócio em execução em simultâneo e retomar o respetivo trabalho na fase no processo em que estavam.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Fluxos do processo de negócio do sistema  
 Estão incluídos os seguintes fluxos do processo de negócio. Para compreender como os fluxos de processos de negócio, leia estes funcionam fluxos de processos de negócio de sistema:  
  
-   Processo de Vendas da Oportunidade Potencial  
  
-   Processo de Vendas da Oportunidade  
  
-   Telefone para Processo de Incidente  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Várias entidades em fluxos do processo de negócio  
 Pode utilizar um fluxo de processos de negócio para uma única entidade ou avaliar várias entidades. Por exemplo, pode ter um processo que comece a uma oportunidade, e continuar a uma proposta, encomenda e, na fatura por último, antes de reverter para fechar a oportunidade.  
  
 Pode conceber os fluxos do processo de negócio que unem nos registos de até cinco entidades diferentes num único processo para as pessoas que utilizam a aplicação poderem concentrar-se no fluxo do respetivo processo em vez de na entidade em que estão a trabalhar. Podem navegar mais facilmente entre registos de entidade relacionados.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Estão disponíveis vários fluxos do processo de negócio por entidade.  
 Não cada utilizador numa organização pode monitorizar o mesmo processo e as circunstâncias diferentes poderão necessitar de um processo diferente que será aplicado. Poderá ter até 10 fluxos de processos ativos de negócio por entidade para fornecer processos adequado para situações diferentes.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Gerir que o fluxo de processos de negócio será aplicado  
 Pode associar fluxos de processos de negócio com o direito de acesso para que apenas os utilizadores com direitos de acesso os podem ver ou utilizar o. Também pode definir a ordem dos fluxos de processos de negócio para que possa gerir que o fluxo de processos de negócio será a predefinição. Isto funciona da mesma forma que os vários formulários para uma entidade estão definidos.  
  
 Quando alguém cria um novo registo de entidade, a lista de definição de processos de negócio ativos disponíveis é filtrada pelo direito de acesso do utilizador. A primeira definição de processo de negócio ativada disponível para o direito de acesso do utilizador de acordo com a lista de ordem de processo é a aplicada por predefinição. Se houver mais de uma definição de processo de negócio ativa, os utilizadores podem carregar outra na caixa de diálogo Mudar de Processo. Sempre que os processos são mudados, o processo atualmente composto passa para segundo plano e é substituído pelo selecionado, mas mantém o respetivo estado e podem ser ativado novamente. Cada registo pode ter várias instâncias do processo associadas (cada uma para uma definição de fluxo do processo de negócio diferente, até um total de 10). Durante o carregamento do formulário só é composto um fluxo do processo de negócio. Quando um utilizador aplica um processo diferente, esse processo só pode ser carregado por predefinição para esse utilizador específico.  
  
 Para garantir que que um processo de negócio é carregado por predefinição para todos os utilizadores (comportamento equivalente a "afixar" o processo), é possível adicionar um script de API de cliente personalizado (recurso Web) durante o carregamento do formulário que carrega especificamente uma instância do processo de negócio existente com base no ID de definição de processo de negócio. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Considerações sobre fluxos de processo de negócio  
 Pode definir fluxos de processos de negócio apenas nas entidades do suporte. Também terá de ter em consideração os limites relativos ao número de processos, fases e passos que podem ser adicionados.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Fluxos de processos de negócio que chamam um fluxo de trabalho  
 Pode chamar fluxos de trabalho a pedido a partir de um fluxo de processo de negócio. É possível configurar esta opção a partir do novo estruturador de fluxos do processo de negócio ao arrastar um componente do fluxo de trabalho para uma fase de processo ou para a secção Fluxos de Trabalho Globais. Para mais informações sobre como utilizar fluxos do processo de negócio, consulte [Blogue: automatização do fluxo do processo de negócio no Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 Quando inclui um fluxo de trabalho que pretende acionar na Saída de Fase de uma fase no seu fluxo do processo de negócio, e essa fase é a última no fluxo, o estruturador dá a impressão de que o fluxo de trabalho será acionado quando a fase for concluída. No entanto, o fluxo de trabalho não será acionado porque uma transição não ocorre. Não receberá um aviso ou um erro que impeça a inclusão do fluxo de trabalho na fase. Quando um utilizador interage com o fluxo do processo de negócio, concluir ou abandonar o processo não resulta numa transição de fase, pelo que o fluxo de trabalho não é acionado. Considere os seguintes exemplos:  
  
-   Crie um fluxo do processo de negócio com duas fases, onde a S1 se liga à S2, com um fluxo de trabalho na fase S2, e defina o acionador para **Saída de Fase**.  
  
-   Crie um fluxo do processo de negócio com três fases, onde S1 se liga à S2 e, em seguida, a S2 cria ramificações para a S3. Inclua um fluxo de trabalho na S2 e defina o acionador como **Saída de Fase**.  
  
 O fluxo de trabalho não será acionado em qualquer caso. Para resolver este problema, poderá adicionar um Fluxo de Trabalho Global e adicionar-lhe o fluxo de trabalho que pretende acionar para o fluxo de trabalho ser acionado para o processo de negócio, em vez de uma fase do processo. Pode definir o acionador de um Fluxo de trabalho global para Processo Abandonado ou Processo Concluído de modo a que o fluxo de trabalho seja acionado quando um utilizador abandonar ou concluir o processo de negócio.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Entidades que podem utilizar fluxos de processos de negócio  
 Todas as entidades personalizadas podem utilizar fluxos de processos de negócio. As entidades padrão que se seguem também podem utilizar fluxos de processos de negócio:  
  
-   Conta  
-   Compromisso  
-   Campanha  
-   Atividade de Campanha  
-   Resultados da Campanha  
-   Concorrente  
-   Contacto  
-   E-mail  
-   Elegibilidade  
-   Fax  
-   Incidente  
-   Fatura  
-   Oportunidade Potencial  
-   Carta  
-   Lista de Marketing  
-   Oportunidade  
-   Chamada Telefónica  
-   Produto  
-   Item da Lista de Preços  
-   Proposta  
-   Compromisso Periódico  
-   Especificações  
-   Atividade de Rede Social  
-   Ordem  
-   Utilizador  
-   Tarefa  
-   Equipa  
  
 Para ativar uma entidade personalizada para fluxos de processos de negócio, selecione a caixa de verificação de **Fluxos de processos de negócio (os campos serão criados)** na definição da entidade. Note que não é possível anular esta ação.  
  
> [!NOTE]
>  Se navega para a fase de fluxo de processos de negócio que contém a entidade de `Social Activity` e escolhe o botão **A fase seguinte** , verá a opção de **Criar** . Quando escolhe **Criar**, o formulário **Atividade de Rede Social** é carregado. No entanto, como `Social Activity` não é válido para `Create` a partir da interface de utilização da aplicação, não poderá guardar o formulário e será apresentada a mensagem de erro: “Erro inesperado”.  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Número máximo de processos, e de fases de passos  
 Para garantir o desempenho e aceitável a utilização da interface de utilizador, existem algumas restrições que tem de estar a par de quando planear utilizar fluxos de processos de negócio:  
  
-   Não pode ter mais de 10 processos de fluxo ativados de processos de negócio por entidade.  
  
-   Cada processo não pode conter mais de 30 fases.  
  
-   os processos de várias entidades não podem conter mais de cinco entidades.
  
## <a name="business-process-flow-entity-customization-support"></a>Suporte de personalização de entidades de fluxos de processo de negócio 

Introduzido no Dynamics 365 (online), versão 9.0, as entidades de fluxo do processo de negócio podem aparecer no sistema para os dados de registo de entidade poderem ser disponibilizadas em grelhas, vistas, gráficos e dashboards. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Utilizar registos de entidade de fluxo do processo de negócio com grelhas, vistas, gráficos e dashboards

Com os fluxos de processos de negócio disponíveis como uma entidade, pode agora utilizar localizações avançadas, vistas, gráficos e dashboards com origem em dados do fluxo de processos de negócio para uma determinada entidade, tal como uma oportunidade potencial ou oportunidade. Os administradores de sistema e personalizadores podem criar dashboards, gráficos, vistas e grelhas do fluxo do processo de negócio personalizados e semelhantes aos criados com qualquer outra entidade.

Os fluxos de processos de negócio, tais como **Processo de Vendas da Oportunidade Potencial**, aparecem sob a forma de uma entidade personalizável no explorador de soluções.

![Explorador de Soluções com a entidade de processo de vendas da oportunidade potencial](media/bpf-lead-solution-explorer.png)

Para aceder a uma vista do do fluxo do processo de negócio, abra o explorador de soluções, expanda **Entidades** > expanda o processo pretendido, tal como **Processo de Vendas da Oportunidade Potencial**, selecione **Vistas** e, em seguida, selecione a vista pretendida.

Estão disponíveis várias vistas predefinidas que podem ser vistas como um gráfico, como a vista **Processo de Vendas da Oportunidade Ativo**. 

![Vista Processo de Vendas da Oportunidade Ativo](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interagir com a entidade de fluxo de processo de negócio a partir de um fluxo de trabalho
Também pode interagir com entidades de fluxos de processo de negócio a partir de um fluxo de trabalho. Pode, por exemplo, criar um fluxo de trabalho para o registo de entidade do Fluxo do Processo de Negócio para alterar a Fase Ativa quando um campo do registo da entidade Oportunidade é atualizado. Para obter mais informações sobre como o fazer, veja [Automate business process flow stages using workflows](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows) (Automatizar fases de fluxos de processos de negócio com fluxos de trabalho).

### <a name="run-business-process-flows-offline"></a>Executar fluxos do processo de negócio offline

Pode utilizar fluxos do processo de negócio offline se as seguintes condições forem cumpridas:

- O fluxo do processo de negócio é utilizado a partir de uma aplicação do Power Apps.
- A aplicação do Power Apps está ativado para utilização offline.
- O fluxo do processo de negócio tem uma única entidade.

Especificamente, os três comandos disponíveis para um fluxo do processo de negócio quando a aplicação do Power Apps está offline são:

- Fase seguinte
- Fase anterior
- Definir Fase ativa

### <a name="limitations-of-using-business-process-flow-entities"></a>Limitações da utilização de entidades de fluxos de processo de negócio

- Atualmente, não pode criar formulários personalizados para entidades com base num fluxo de processo de negócio.
- Se uma solução incluir uma entidade de fluxo de processo de negócio, essa entidade terá de ser adicionada manualmente à solução antes de a exportar. Caso contrário, a entidade de fluxo de processo de negócio não será incluída no pacote de solução. Mais informações: [Add solution components](/powerapps/maker/model-driven-apps/create-solution#add-solution-components) (Adicionar componentes da solução)
- A adição da entidade do processo a uma aplicação condicionada por modelo poderá limitar a funcionalidade. Saiba mais sobre a [criação e edição de fluxos de processos de negócio](https://docs.microsoft.com/power-automate/create-business-process-flow). 

### <a name="next-steps"></a>Passos seguintes  
 [Assista a um pequeno vídeo (4:49) sobre os fluxos do processo de negócio](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Criar um fluxo de processo de negócio](create-business-process-flow.md)   
 [Melhorar fluxos de processos de negócio com ramificação](enhance-business-process-flows-branching.md) <br/>
 [Whitepaper: Process Enablement with Dynamics 365](https://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf) (Documento Técnico: Ativação de Processos com o Dynamics 365)</br>
