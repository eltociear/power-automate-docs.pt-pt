---
title: Melhorar os fluxos de processos de negócio com ramificação com o Power Apps | Microsoft Docs
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
ms.openlocfilehash: 577bad2fa7e0db66c95fae5668c4a576e3c3a2d7
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74365184"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Tutorial: Melhorar fluxos de processos de negócio com ramificação
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Os fluxos de processos de negócio orientam-no ao longo de várias fases dos processos de vendas, marketing ou serviço até à respetiva conclusão. Em casos simples, um fluxo de processo de negócio linear é uma boa opção. No entanto, em cenários mais complexos, pode melhorar um fluxo de processo de negócio através da ramificação. Se tiver as permissões de criação em fluxos de processos de negócio, será capaz de criar um fluxo de processo de negócio com múltiplas ramificações através da lógica `If-Else`. A condição de ramificação pode incluir múltiplas expressões lógicas que utilizam uma combinação de operadores `AND` ou `OR`. A seleção da ramificação é feita automaticamente, em tempo real e com base em regras definidas durante a definição do processo. Por exemplo, na venda de automóveis, pode configurar um único fluxo de processo de negócio que se divida em duas ramificações separadas com base numa regra após uma fase de qualificação comum (o cliente prefere um automóvel novo ou usado, o orçamento dele está acima ou abaixo dos 20 mil €, etc. ): uma ramificação para vender automóveis novos e outra ramificação para vender automóveis usados. Para obter mais informações sobre Fluxos de processos de negócio, veja [Descrição geral dos fluxos de processos de negócio](business-process-flows-overview.md).  
  
 O diagrama seguinte mostra um fluxo de processo de negócio com ramificações.  
  
 ![Fluxograma a mostrar os passos no processo de venda de automóveis](media/example-car-sales-flow-chart.png "Fluxograma a mostrar os passos no processo de venda de automóveis")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>O que precisa de saber ao estruturar fluxos de processos de negócio com ramificações  
 Tenha as seguintes informações em atenção ao estruturar o fluxo de processo de negócio com ramificações:  
  
-   Cada processo pode abranger, no máximo, de cinco entidades únicas.  
  
-   Pode utilizar até 30 fases por processo e até 30 passos por fase.  
  
-   Cada ramificação não pode ter mais do que cinco níveis.  
  
-   A regra de ramificação tem de se basear nos passos da fase imediatamente anterior.  
  
-   Pode combinar múltiplas condições numa regra ao utilizar o operador `AND` ou o operador `OR`, mas não os dois.  
  
-   Quando definir um fluxo de processo, pode opcionalmente, selecionar uma relação entre entidades. Esta relação tem de ser uma relação entre entidades 1:N (um-para-muitos).  
  
-   É possível executar mais do que um processo ativo em simultâneo no mesmo registo de dados.  
  
-   Pode reorganizar os mosaicos (Fases, Passos, Condições, etc.) no fluxo do processo ao arrastar e largar.  
  
-   Quando unir ramificações, todas as ramificações do mesmo nível têm de ser unidas numa única fase. Todas as ramificações do mesmo nível têm de ser unidas numa única fase ou cada ramificação do mesmo nível tem de terminar o processo. Uma ramificação do mesmo nível não pode unir-se a outras ramificações e terminar o processo em simultâneo.  
  
> [!NOTE]
> - É possível revisitar uma entidade utilizada no processo múltiplas vezes (múltiplos ciclos de entidade fechados).  
> - Os processos podem voltar à fase anterior independentemente do tipo de entidade. Por exemplo, se a fase ativa for **Entregar Proposta** num registo de proposta, os utilizadores do processo podem mover novamente a fase ativa para a fase **Propor** num registo de oportunidade.  
>   
>   Para dar outro exemplo, imagine que um processo está atualmente na fase **Apresentar Proposta** do seu fluxo do processo **Qualificar Oportunidade Potencial** > **Identificar Necessidades** > **Criar Proposta** > **Apresentar Proposta** > **Fechar**. Se for necessário fazer mais pesquisa para identificar as necessidades do cliente no âmbito da proposta apresentada ao mesmo, os utilizadores podem simplesmente selecionar a fase **Identificar Necessidades** do seu processo e selecionar **Definir como Ativo**.  
  
<a name="CarSelling365"></a>   
## <a name="example-car-selling-process-flow-with-two-branches"></a>Exemplo: Fluxo do processo de venda de automóveis com duas ramificações
 
Vejamos o exemplo do fluxo de processo de negócio com duas ramificações: uma relativa à venda de automóveis novos e outra relativa à venda de automóveis usados.  
  
 Em primeiro lugar, vamos criar um novo processo com o nome **Processo de Vendas de Automóveis**.  
  
1.  [Abra o explorador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e, em seguida, selecione **Processos** no painel de navegação esquerdo.  
  
2.  Selecione **Novo** para criar um novo processo.  
  
3.  Defina a **Categoria** para **Fluxo do Processo de Negócio** e, para a **Entidade** primária, selecione **Oportunidade Potencial**.  
  
4.  Adicione a primeira fase ao processo chamado **Qualificação** e adicione passos os **Período de Tempo de Compra** e **Preferência de Automóvel**.  
  
5.  Após a fase **Qualificação** comum, dividimos o processo em duas ramificações separadas ao utilizar o mosaico **Condição**.  
  
    1.  Configurar o mosaico da condição com regras que satisfazem os seus requisitos de negócio  
  
    2.  Para adicionar a primeira ramificação a uma fase, adicione um mosaico de fase no caminho "Sim" do mosaico de condição.  
  
    3.  Para adicionar a segunda ramificação que é executada quando a condição não é satisfeita, adicione outro mosaico de fase no caminho "Não" do mosaico de condição.  
  
> [!TIP]
>  É possível adicionar outra condição no caminho "não" de um mosaico de condição existente para criar uma ramificação mais complexa.  
  
 ![Imagem a mostrar a fase Qualificar criada](media/example-car-sales-qualify-stage.JPG "Imagem a mostrar a fase Qualificar criada")  
  
 Se **Preferência de Automóvel** = **Novo**, o processo ramifica-se para a fase **Vendas de Automóveis Novos**, caso contrário, avança para a fase **Vendas de Automóveis Usados** na segunda ramificação, conforme mostrado abaixo.  
  
 ![Imagem a mostrar a fase Venda de Automóveis Novos](media/example-car-sales-new-stage-1.JPG "Imagem a mostrar a fase Venda de Automóveis Novos")  
  
 ![Fase Venda de Automóveis Usados](media/example-car-sales-pre-owned-stage.JPG "Fase Venda de automóveis usados")  
  
 Depois de concluir todos os passos da fase **Vendas de Automóveis Novos** ou da fase **Vendas de Automóveis Usados**, o processo regressa ao fluxo principal com a fase **Entregar Proposta**.  
  
 ![Fase Entregar Proposta](media/example-car-sales-deliver-quote-stage.JPG "Fase Entregar Proposta")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Impedir a divulgação de informações  
 Considere um fluxo de processo de negócio com ramificações para processar um pedido de empréstimo bancário, conforme mostrado abaixo. As entidades personalizadas utilizadas nas fases encontram-se entre parêntesis.  
  
 ![Fluxograma a mostrar os passos num processo de exemplo para impedir a divulgação de informações](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Fluxograma a mostrar os passos num processo de exemplo para impedir a divulgação de informações")  
  
 Neste cenário, a gestora de créditos do banco precisa de ter acesso ao Registo de pedidos, mas não deve conseguir ver a investigação do pedido. À primeira vista, parece que podemos fazer isso facilmente ao atribuir à gestora de créditos uma função de segurança que especifica a inexistência de acesso à entidade Investigação. Contudo, vamos examinar o exemplo mais detalhadamente e ver se isso é mesmo verdade.  
  
 Imaginemos que um cliente pede um empréstimo ao banco superior a 60 000 €. A gestora de créditos revê o pedido na primeira fase. Se a regra de ramificação que verifica se o montante devido ao banco excederá 50 000 € for satisfeita, a próxima fase do processo consiste em investigar se o pedido é fraudulento. Caso se chegue à conclusão de que este caso é mesmo uma fraude, o processo avança para a aplicação de uma ação judicial contra o requerente. A gestora de créditos não deve conseguir ver as duas fases de investigação, uma vez que não tem acesso à entidade Investigação.  
  
 No entanto, se abrir o Registo de pedidos, conseguirá ver todo o processo de ponto a ponto. Não só conseguirá ver a fase de investigação da fraude, como também conseguirá identificar o resultado da investigação devido ao facto de ter conseguido ver a fase Ação Judicial no processo. Além disso, poderá pré-visualizar os passos nas fases de investigação ao selecionar a fase. Embora não vá conseguir ver os dados nem o estado de conclusão dos passos, vai conseguir identificar as potenciais ações que foram realizadas contra o requerente durante as fases de investigação e ação judicial.  
  
 Neste fluxo do processo, a gestora de créditos conseguirá ver as fases Investigação de Fraude e Ação Judicial, o que constitui uma divulgação de informações imprópria. Recomendamos que preste especial atenção às informações que poderão ser divulgadas devido à ramificação. No nosso exemplo, divida o processo em dois processos separados, um para o processamento do pedido e outro para a investigação de fraude, de forma a impedir a divulgação de informações. Para a gestora de créditos, o processo terá o seguinte aspeto:  
  
 ![Fluxograma a mostrar os passos adicionais num processo para impedir a divulgação de informações](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Fluxograma a mostrar os passos adicionais num processo para impedir a divulgação de informações")  
  
 O processo da investigação será autónomo e incluirá as seguintes fases:  
  
 ![Fluxograma a mostrar os passos de um processo de investigação para casos de divulgação de informações](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Fluxograma a mostrar os passos de um processo de investigação para casos de divulgação de informações")  
  
 Terá de fornecer um fluxo de trabalho para sincronizar a decisão Aprovar/Negar do registo Investigação para o registo Pedido.  
  
### <a name="next-steps"></a>Passos seguintes  
 [Criar um fluxo de processo de negócio](create-business-process-flow.md)   
 [Criar lógica de negócio personalizada através de processos](guide-staff-through-common-tasks-processes.md)   
 
