---
title: Melhorar fluxos de processos de negócio com ramificação com o Power Apps | MicrosoftDocs
description: Saiba como utilizar a ramificação num fluxo de processo de negócio
ms.custom: ''
ms.date: 06/27/2018
ms.tgt_pltfrm: ''
ms.topic: article
ms.service: flow
author: MSFTMAN
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: Deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2fedda5160291362d1ff4fcbcf91cec9f4e78713
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297896"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Tutorial: Melhorar fluxos de processos de negócio com ramificação


Os fluxos de processos de negócio orientam-no ao longo de várias fases dos processos de vendas, marketing ou serviço até à respetiva conclusão. Em incidentes simples, fluxo de um processo de negócio do é uma boa opção. Contudo, cenários nas mais complexas, pode aumentar um fluxo de processos de negócio com ramificação. Se tiver permissões para criar fluxos o processo de negócio, só poderá criar o fluxo de processos de negócio com os vários utilizar ramos lógica de `If-Else` . A condição de ramificação pode ser formada por várias expressões lógicos que utilizem uma combinação de operadores `AND` ou `OR`. A seleção de ramos é efetuada automaticamente, em tempo real, com base nas regras que definiu durante a definição de processo. Por exemplo, para vender carros, pode configurar um único fluxo de processos de negócio, após uma fase qualificação comum ser dividida em dois ramos separados com base numa regra (o cliente prefere um carro novo ou em segunda mão, o orçamento é superior a 20.000€, etc. ) um ramo para vender carros novos e outro para vender carros usados. Para mais informações sobre Fluxos do processo de negócio, consulte [Descrição geral de fluxos do processo de negócio](business-process-flows-overview.md).  
  
 O diagrama seguinte mostra um fluxo de processos de negócio com ramos.  
  
 ![Fluxograma a mostrar os passos no processo de venda de automóveis](media/example-car-sales-flow-chart.png "Fluxograma a mostrar os passos no processo de venda de automóveis")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>O que precisa de saber ao estruturar fluxos de processos de negócio com ramos  
 Aviso de efectuada de seguintes informações quando conceber o fluxo de processos de negócio com os ramos:  
  
-   Pode medir um processo com um máximo de 5 entidades documentos.  
  
-   Pode utilizar um máximo de 30 fases no processo e um máximo de 30 passos pela fase.  
  
-   Cada ramo não pode ser um máximo de 5 profundamente níveis.  
  
-   A regra tem de ser de ramificação baseada nos passos na fase da precede imediatamente.  
  
-   Pode fazer corresponder várias condições numa regra utilizando o operador de `AND` ou operador de `OR` , mas não ambos os operadores.  
  
-   Quando define um fluxo de processo opcionalmente, pode selecionar uma relação entre entidades. Este tem uma relação 1:N (um-para-muitos) entre entidades.  
  
-   Mais de um processo activo pode ser executado em simultâneo no mesmo registo dados.  
  
-   Pode reorganizar mosaicos (Fases, Passos, Condições etc.) no fluxo do processo utilizando arrastar e largar.  
  
-   A intercalar ramos, todos os ramos de registo têm intercalar a uma fase. Os ramos de registo têm qualquer ou impressão numa única cada fase, ou ramo de registo deve concluir o processo. Um ramo de registo não é possível intercalar com outros ramos e simultaneamente concluir o processo.  
  
> [!NOTE]
> - Uma entidade utilizada no processo pode ser revisitada várias vezes (fechadas vários ciclos de entidade).  
> - Um processo pode regressar à fase anterior independentemente de um tipo de entidade. Por exemplo, se a fase ativa é **Entregar Proposta** num registo de proposta, os utilizadores do processo podem passar a fase ativa para a fase **Proposta** de um registo de oportunidade.  
>   
>   Noutro exemplo, vamos supor que um processo está atualmente na fase **Apresentar Proposta** do fluxo de processo: **Qualificar Oportunidade Potencial** > **Identificar Necessidades** > **Criar Proposta** > **Apresentar Proposta** > **Fechar**. Se a proposta apresentada ao cliente necessitar de mais investigação para identificar as necessidades do cliente, os utilizadores podem simplesmente selecionar a fase **Identificar Necessidades** do processo e selecionar **Definir como Ativo**.  
  
<a name="CarSelling365"></a>   
## <a name="example-car-selling-process-flow-with-two-branches"></a>Exemplo: Fluxo de processo de venda de carro com dois ramos
 
Vejamos o exemplo do fluxo de processo de negócio com duas ramificações: uma relativa à venda de automóveis novos e outra relativa à venda de automóveis usados.  
  
 Primeiro, vamos criar um novo processo chamado **Processo de Venda de Veículos Automóveis**.  
  
1.  [Abra o explorador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e, em seguida, selecione **Processos** no painel de navegação esquerdo.  
  
2.  Selecione **Novo** para criar um novo processo.  
  
3.  Especifique a **Categoria** como **Fluxo do Processo de Negócio** e, para **Entidade** primária, selecione **Oportunidade potencial**.  
  
4.  Adicione a primeira fase do processo, chamada **Qualificar**, e adicione os passos **Intervalo de Tempo de compra** e **Preferência de Carro**.  
  
5.  Após a fase comum **Qualificar** , iremos dividir o processo em dois ramos separados, utilizando o mosaico **Condição**.  
  
    1.  Configurar o mosaico condição com regras que satisfazem as suas necessidades de negócio  
  
    2.  Para adicionar a primeira ramificação a uma fase, adicione um mosaico Fase no caminho "Sim" do mosaico da condição  
  
    3.  Para adicionar a segunda ramificação que é executada quando condição não é satisfeita, adicione outro mosaico Fase no caminho "Não" do mosaico da condição  
  
> [!TIP]
>  Pode adicionar outra condição no caminho "não" de um mosaico de condição existente para criar uma ramificação mais complexa.  
  
 ![Imagem a mostrar a fase Qualificar criada](media/example-car-sales-qualify-stage.JPG "Imagem a mostrar a fase Qualificar criada")  
  
 Se a **Preferência de carro** = **Novo**, o processo ramifica para a fase **Venda de Carro Novo**, caso contrário, salta para a fase **Venda de Carro Usado**, na segunda ramificação, conforme mostrado abaixo.  
  
 ![Imagem que mostra a fase Venda de Carro Novo](media/example-car-sales-new-stage-1.JPG "Imagem que mostra a fase Venda de Carro Novo")  
  
 ![Fase de venda de carro usado](media/example-car-sales-pre-owned-stage.JPG "Fase de venda de carro usado")  
  
 Depois de concluído todos os passos na fase de **Carro novo Vendas** ou na fase de **Carro utilizado Vendas** , os resultados do processo novamente para o fluxo principal, a fase de **Entregue a proposta** .  
  
 ![Fase Entregar Proposta](media/example-car-sales-deliver-quote-stage.JPG "Fase Entregar Proposta")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Impedir a divulgação de informações  
 Considere um fluxo de processos de negócio com ramos para processar um pedido de empréstimo numa base, conforme mostrado abaixo. As entidades personalizadas utilizadas nas fases são apresentadas em parêntese.  
  
 ![Fluxograma a mostrar os passos num processo de exemplo para impedir a divulgação de informações](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Fluxograma a mostrar os passos num processo de exemplo para impedir a divulgação de informações")  
  
 Neste cenário, a gestora de créditos do banco precisa de ter acesso ao Registo de pedidos, mas não deve conseguir ver a investigação do pedido. À primeira vista, parece que poderemos fazê-lo facilmente atribuindo ao agente de crédito um direito de acesso que especifique que este não tem acesso à entidade Investigação. No entanto, vamos observar o exemplo mais detalhadamente para ver se isto é realmente verdadeiro.  
  
 Vamos ver o que um cliente coloque o pedido de empréstimo para mais do $60.000 base. O agente de crédito reveja o pedido na primeira fase. Se a regra de ramificação que verifica se o montante para a base excederá é $50.000 satisfeita, a fase seguinte no processo é investigar se o pedido é fraudulento. Se se determinar que este é realmente um incidente de fraude, o processo avança para a tomada de uma ação jurídica contra o solicitante. A gestora de créditos não deve conseguir ver as duas fases de investigação, uma vez que não tem acesso à entidade Investigação.  
  
 No entanto, se abrir o Registo de pedidos, conseguirá ver todo o processo de ponto a ponto. Não só conseguirá ver a fase de investigação da fraude, como também conseguirá identificar o resultado da investigação devido ao facto de ter conseguido ver a fase Ação Judicial no processo. Além disso, poderá pré-visualizar os passos nas fases de investigação ao selecionar a fase. Embora não vá conseguir ver os dados nem o estado de conclusão dos passos, vai conseguir identificar as potenciais ações que foram realizadas contra o requerente durante as fases de investigação e ação judicial.  
  
 Neste fluxo de processo, o agente de crédito poderá ver as fases de investigação de fraude e da ação jurídica, que constitui essa divulgação incorreta das informações. Recomendamos a atenção de pagamento especial com as informações que se pode tornar divulgado devido a ramificação. No nosso exemplo, subdivida o processo em processos separados, um para o pedido ao processar e outro para a fraude de investigação, para impedir a divulgação das informações. O processo do agente de crédito terá o seguinte aspeto:  
  
 ![Fluxograma a mostrar passos adicionais no processo para impedir a divulgação de informações](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Fluxograma a mostrar passos adicionais no processo para impedir a divulgação de informações")  
  
 O processo da investigação será independentemente e incluirá as seguintes fases:  
  
 ![Fluxograma a mostrar os passos para um processo de investigação para casos de divulgação de informações](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Fluxograma a mostrar os passos para um processo de investigação para casos de divulgação de informações")  
  
 Terá de fornecer um fluxo de trabalho para sincronizar a decisão Aprovar/Negar do registo Investigação para o registo Pedido.  
  
### <a name="next-steps"></a>Passos seguintes  
 [Criar um fluxo de processo de negócio](create-business-process-flow.md)   
 [Criar lógica empresarial personalizada com processos](guide-staff-through-common-tasks-processes.md)   
 
