---
title: Descrição geral dos fluxos de processos de negócio | Microsoft Docs
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
ms.locfileid: "80624852"
---
# <a name="business-process-flows-overview"></a>Descrição geral dos fluxos de processos de negócio


Ao criar um fluxo de processo de negócio, pode ajudar a garantir que as pessoas introduzem os dados de forma consistente e seguem os mesmos passos sempre que trabalharem com um cliente. Por exemplo, é recomendado que crie um fluxo de processo de negócio para que todas as pessoas lidem com os pedidos de serviço de cliente da mesma forma ou para exigir que as pessoas obtenham aprovação para uma fatura antes de submeterem uma encomenda. Os fluxos de processos de negócio utilizam a mesma tecnologia subjacente a outros processos, mas as capacidades que proporcionam são muito diferentes de outras funcionalidades que utilizam processos. Para saber como criar ou editar um fluxo de processo de negócio, veja [Criar um fluxo do processo de negócio](create-business-process-flow.md).  
  
 [Veja um breve vídeo (4:49) sobre os fluxos de processos de negócio.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Porquê utilizar fluxos de processos de negócio?  
Os fluxos de processos de negócio orientam as pessoas para que consigam realizar o respetivo trabalho. Proporcionam uma experiência de utilizador otimizada e orientam as pessoas ao longo dos processos que a organização delas definiu relativamente às interações que têm de avançar para se chegar a algum tipo de conclusão. Esta experiência de utilizador pode ser adaptada para que as pessoas com diferentes funções de segurança possam ter a experiência que melhor se adeque ao trabalho que desempenham.  
  
 Utilize fluxos de processos de negócio para definir um conjunto de passos que as pessoas deverão seguir para alcançarem um resultado pretendido. Estes passos proporcionam um indicador visual que permite que as pessoas saibam em que fase do processo de negócio se encontram. Os fluxos de processos de negócio reduzem a necessidade de formação, uma vez que os novos utilizadores não precisam de se concentrar para saber a entidade que deveriam estar a utilizar. Podem deixar que o processo os oriente. Pode configurar fluxos de processos de negócio para suportarem metodologias de venda comuns que podem ajudar os seus grupos de vendas a alcançarem melhores resultados. No caso dos grupos de serviço, os fluxos de processos de negócio podem ajudar os novos colaboradores a manterem-se atualizados mais rapidamente e a evitarem erros que poderiam resultar na insatisfação dos clientes.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>O que é que os fluxos de processos de negócio conseguem fazer?  
 Com os fluxos de processos de negócio, pode definir um conjunto de *fases* e *passos* que são apresentados num controlo localizado na parte superior do formulário.  
  
 ![Processo de negócio com fases](media/business-process-stages.png "Processo de negócio com fases")  
  
 Cada fase contém um grupo de passos. Cada passo representa um campo onde é possível introduzir dados. As pessoas podem avançar para a próxima fase através do botão **Fase Seguinte**. Pode tornar um passo obrigatório para que as pessoas tenham de introduzir dados no campo correspondente antes de poderem avançar para a fase seguinte. Isto é frequentemente designado como "controlo de fases".  
  
 Os fluxos de processos de negócio parecem ser relativamente simples em comparação com outros tipos de processos porque não fornecem nenhuma automatização ou lógica de negócio condicional – apenas proporcionam a experiência otimizada de introdução de dados e de controlo da entrada nas fases. No entanto, quando os combina com outros processos e personalizações, estes fluxos podem desempenhar um papel importante ao permitir que as pessoas poupem tempo, ao reduzir os custos de formação e ao aumentar a adoção por parte dos utilizadores.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Fluxos de processos de negócio integrados com outras personalizações  
 Quando você, ou o seu utilizador, introduz dados com os fluxos de processos de negócio, as alterações aos dados também são aplicadas a campos de formulário para que a automatização proporcionada pelas regras de negócio ou pelos scripts de formulário possam ser aplicadas imediatamente. É possível adicionar passos que definem valores para campos que não estão presentes no formulário. Estes campos serão adicionados ao modelo de objeto `Xrm.Page` utilizado para scripts de formulário. Os fluxos de trabalho que são iniciados por alterações aos campos incluídos num fluxo de processo de negócio serão aplicados quando os dados presentes no formulário forem guardados. Se a automatização for aplicada por um fluxo de trabalho em tempo real, as alterações ficarão imediatamente visíveis para o utilizador quando os dados presentes no formulário forem atualizados depois de o registo ser guardado.  
  
 Embora o controlo do fluxo de processo de negócio no formulário não proporcione nenhuma programação direta do lado do cliente, as alterações aplicadas por regras de negócio ou scripts de formulário são automaticamente aplicadas aos controlos de fluxo de processo de negócio. Se ocultar um campo num formulário, esse campo também ficará ocultado no controlo do fluxo de processo de negócio. Se definir um valor através de regras de negócio ou scripts de formulário, esse valor será definido dentro do fluxo de processo de negócio.  
  
### <a name="concurrent-process-flows"></a>Fluxos de processos em simultâneo  
 Os fluxos de processos de negócio em simultâneo permitem que os personalizadores configurem múltiplos processos de negócio e os associem ao mesmo registo de partida. Os utilizadores podem alternar entre múltiplos processos de negócio que estejam a ser executados em simultâneo e retomar o respetivo trabalho na fase do processo em que se encontravam.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Fluxos de processos de negócio do sistema  
 Estão incluídos os fluxos de processos de negócio que se seguem. Para compreender a forma como os fluxos de processos de negócio funcionam, reveja estes fluxos de processos de negócio do sistema:  
  
-   Processo de Vendas da Oportunidade Potencial  
  
-   Processo de Vendas da Oportunidade  
  
-   Processo de Telefone para Incidente  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Múltiplas entidades em fluxos de processos de negócio  
 Pode utilizar um fluxo do processo de negócio para uma entidade ou para múltiplas entidades. Por exemplo, poderá ter um processo que começa com uma oportunidade e que avança para uma proposta, uma encomenda e uma fatura, antes de finalmente fechar a oportunidade.  
  
 Pode estruturar fluxos de processos de negócio que reúnam os registos de, no máximo, cinco entidades diferentes num único processo para que os utilizadores da aplicação possam concentrar-se no fluxo do respetivo processo, em vez de na entidade na qual estão a trabalhar. Desta forma, os utilizadores podem navegar mais facilmente entre registos de entidade associados.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Estão disponíveis múltiplos fluxos de processos de negócio por entidade  
 Nem todos os utilizadores numa organização poderão seguir o mesmo processo. Além disso, condições diferentes podem exigir a aplicação de um processo diferente. Pode ter até 10 fluxos de processos de negócio ativos por entidade para proporcionar processos adequados para diferentes situações.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Controlar o fluxo de processo de negócio que será aplicado  
 Pode associar fluxos de processo de negócio a funções de segurança para que apenas as pessoas com essas funções possam vê-los ou utilizá-los. Também pode definir a ordem dos fluxos de processos de negócio para que possa controlar o fluxo do processo de negócio que será predefinido. Este procedimento é igual ao da definição de múltiplos formulários para uma entidade.  
  
 Quando alguém cria um novo registo de entidade, a lista de definições de processos de negócio ativas e disponíveis é filtrada pela função de segurança do utilizador. A primeira definição de processo de negócio ativada que está disponível para a função de segurança do utilizador, de acordo com a lista da ordem do processo, é aplicada por predefinição. Se estiver disponível mais do que uma definição de processo de negócio ativa, os utilizadores podem carregar outro processo a partir da caixa de diálogo Mudar de Processo. Sempre que existir uma mudança de processo, o processo que está a ser composto atualmente vai para segundo plano e é substituído pelo que está selecionado, mas mantém o respetivo estado e pode ser mudado novamente. Cada registo pode ter múltiplas instâncias de processo associadas (cada uma para uma definição de fluxo de processo de negócio diferente, até um total de 10). Durante o carregamento de formulários, só é composto um fluxo de processo de negócio. Quando um utilizador aplicar um processo diferente, esse processo só poderá ser carregado, por predefinição, para esse utilizador específico.  
  
 Para se certificar de que um processo de negócio é carregado por predefinição para todos os utilizadores (comportamento equivalente à "afixação" do processo), pode adicionar uma API de Cliente personalizada (recurso Web) durante o carregamento do formulário que carrega especificamente uma instância existente do processo de negócio com base no ID da definição do processo de negócio. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Considerações sobre fluxos de processo de negócio  
 Só pode definir fluxos de processos de negócio para as entidades os suportam. Também terá de ter em consideração os limites relativos ao número de processos, fases e passos que podem ser adicionados.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Fluxos de processos de negócio que chamam um fluxo de trabalho  
 Pode chamar fluxos de trabalho a pedido a partir de um fluxo de processo de negócio. Pode configurar isto a partir do novo estruturador de fluxos de processos de negócio ao arrastar um componente de fluxo de trabalho para uma fase do processo ou para a secção dos Fluxos de Trabalho Globais. Para obter mais informações sobre a utilização de fluxos de trabalho em fluxos do processo de negócio, veja [Blog: Business process flow automation in Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/) (Blogue: Automatização de fluxos do processo de negócio no Dynamics 365).  
  
 Quando inclui um fluxo de trabalho que pretende acionar à Saída de Fase de uma fase do seu fluxo de processo de negócio e essa fase é a última do fluxo, o estruturador dá a impressão de que o fluxo de trabalho será acionado quando essa fase é concluída. No entanto, o fluxo de trabalho não será acionado porque não ocorre uma transição de fase. Não receberá um aviso ou erro que o impedirá de incluir o fluxo de trabalho na fase. Quando um utilizador interage com o fluxo de processo de negócio, a conclusão ou o abandono do processo não resulta numa transição de fase, pelo que o fluxo de trabalho não é acionado. Considere os seguintes exemplos:  
  
-   Cria um fluxo do processo de negócio com duas fases (a S1 liga à S2) com um fluxo de trabalho na fase S2 e define o acionador para a **Saída de Fase**.  
  
-   Cria um fluxo do processo de negócio com três fases: a S1 liga à S2 e esta última ramifica-se na S3. Inclui um fluxo de trabalho na S2 e define o acionador para a **Saída de Fase**.  
  
 O fluxo de trabalho não será acionado em nenhum dos casos. Para contornar este problema, pode adicionar um Fluxo de Trabalho Global e adicionar o fluxo de trabalho para o qual pretende acionar para que o fluxo de trabalho seja acionado para o processo de negócio em vez de para uma fase do processo. Pode definir o acionador de um Fluxo de trabalho global para Processo Abandonado ou Processo Concluído de modo a que o fluxo de trabalho seja acionado quando um utilizador abandonar ou concluir o processo de negócio.  
  
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
-   Cliente potencial  
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
-   Encomenda  
-   Utilizador  
-   Tarefa  
-   Equipa  
  
 Para ativar uma entidade personalizada para fluxos de processos de negócio, selecione a caixa de verificação **Fluxos do processo de negócio (serão criados campos)** na definição da entidade. Tenha em atenção que não é possível anular esta ação.  
  
> [!NOTE]
>  Se navegar para a fase do fluxo de processo de negócio que contém a entidade `Social Activity` e selecionar o botão **Fase Seguinte**, verá a opção **Criar**. Quando selecionar **Criar**, o formulário **Atividade de Rede Social** é carregado. No entanto, como a `Social Activity` não é válida para `Create` a partir da interface de utilizador da aplicação, não conseguirá guardar o formulário e verá a mensagem de erro: "Erro inesperado".  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Número máximo de processos, fases e passos  
 Para garantir um desempenho aceitável e a usabilidade da interface de utilizador, existem algumas limitações que tem de conhecer quando planear utilizar fluxos de processos de negócio:  
  
-   Não podem existir mais do que 10 processos de fluxo de processo de negócio ativados por entidade.  
  
-   Cada processo só pode conter até 30 fases.  
  
-   Os processos com múltiplas entidades só podem conter até cinco entidades.
  
## <a name="business-process-flow-entity-customization-support"></a>Suporte de personalização de entidades de fluxos de processo de negócio 

As entidades de fluxos de processos de negócio, introduzidas na atualização relativa à versão 9.0 do Dynamics 365 (online), podem aparecer no sistema para que os dados de registos de entidade possam ser disponibilizados em grelhas, vistas, gráficos e dashboards. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Utilizar registos de entidade de fluxos de processo de negócio com grelhas, vistas, gráficos e dashboards

Como agora os fluxos de processos de negócio estão disponíveis sob a forma de entidades, pode utilizar localizações, vistas, gráficos e dashboards avançados com origem em dados de fluxos de processos de negócio de uma determinada entidade, tal como de uma oportunidade potencial ou de uma oportunidade. Os administradores de sistema e personalizadores podem criar grelhas, vistas, gráficos e dashboards de fluxos de processos de negócio personalizados semelhantes aos criados com qualquer outra entidade.

Os fluxos de processos de negócio, tais como **Processo de Vendas da Oportunidade Potencial**, aparecem sob a forma de uma entidade personalizável no explorador de soluções.

![Explorador de Soluções com a entidade de processo de vendas da oportunidade potencial](media/bpf-lead-solution-explorer.png)

Para aceder a uma vista predefinida de fluxo de processo de negócio, abra o explorador de soluções, expanda **Entidades** > expanda o processo que pretende, tal como **Processo de Vendas da Oportunidade Potencial**, selecione **Vistas** e, em seguida, selecione a vista que pretende.

Estão disponíveis várias vistas predefinidas que pode ver sob a forma de um gráfico, tal como a vista **Processo de Vendas da Oportunidade Ativo**. 

![Vista Processo de Vendas da Oportunidade Ativo](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interagir com a entidade de fluxo de processo de negócio a partir de um fluxo de trabalho
Também pode interagir com entidades de fluxos de processo de negócio a partir de um fluxo de trabalho. Pode, por exemplo, criar um fluxo de trabalho para o registo de entidade do Fluxo do Processo de Negócio para alterar a Fase Ativa quando um campo do registo da entidade Oportunidade é atualizado. Para obter mais informações sobre como o fazer, veja [Automate business process flow stages using workflows](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows) (Automatizar fases de fluxos de processos de negócio com fluxos de trabalho).

### <a name="run-business-process-flows-offline"></a>Executar fluxos do processo de negócio offline

Pode utilizar fluxos do processo de negócio offline se as seguintes condições forem cumpridas:

- O fluxo do processo de negócio é utilizado a partir de uma aplicação do Power Apps.
- A aplicação do Power Apps está ativada para utilização offline.
- O fluxo do processo de negócio tem uma única entidade.

Especificamente, os três comandos disponíveis para um fluxo do processo de negócio quando a aplicação do Power Apps está offline são:

- Fase seguinte
- Fase anterior
- Definir Fase ativa

### <a name="limitations-of-using-business-process-flow-entities"></a>Limitações da utilização de entidades de fluxos de processo de negócio

- Atualmente, não pode criar formulários personalizados para entidades com base num fluxo de processo de negócio.
- Se uma solução incluir uma entidade de fluxo de processo de negócio, essa entidade terá de ser adicionada manualmente à solução antes de a exportar. Caso contrário, a entidade de fluxo de processo de negócio não será incluída no pacote de solução. Mais informações: [Adicionar componentes da solução](/powerapps/maker/model-driven-apps/create-solution#add-solution-components)
- A adição da entidade do processo a uma aplicação condicionada por modelo poderá limitar a funcionalidade. Saiba mais sobre a [criação e edição de fluxos de processos de negócio](https://docs.microsoft.com/power-automate/create-business-process-flow). 

### <a name="next-steps"></a>Próximos passos  
 [Veja um breve vídeo (4:49) sobre fluxos de processos de negócio](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Criar um fluxo de processo de negócio](create-business-process-flow.md)   
 [Melhorar fluxos de processos de negócio com ramificação](enhance-business-process-flows-branching.md) <br/>
 [Whitepaper: Process Enablement with Dynamics 365](https://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf) (Documento Técnico: Ativação de Processos com o Dynamics 365)</br>
