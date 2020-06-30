---
title: Substituir fluxos de trabalho clássicos do Common Data Service pelo Power Automate | Microsoft Docs
description: Descreve as capacidades do Power Automate e os padrões recomendados para utilizar fluxo, em vez de um fluxo de trabalho clássico.
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
ms.service: flow
ms.topic: article
ms.date: 05/12/2020
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 008a07cf5ee24b5de6d740cc19ee1f5219d86b76
ms.sourcegitcommit: b872a664a8adcdfb3db5a4ec861c23eea883a71e
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/12/2020
ms.locfileid: "3367735"
---
# <a name="replace-classic-common-data-service-workflows-with-flows"></a>Substituir fluxos de trabalho clássicos do Common Data Service por fluxos


Este tópico compara as capacidades do Power Automate com as de um fluxo de trabalho clássico.

O Power Automate tem vantagens significativas em relação ao modelo de fluxo de trabalho clássico; deve considerar utilizar o Power Automate para automatizar os seus processos, em vez de utilizar um fluxo de trabalho clássico. 

Crie fluxos em vez de fluxos de trabalho do Common Data Service clássicos para criar novos processos de automatização. Além disso, deve rever os processos de fluxo de trabalho clássicos existentes e considerar substituí-los por fluxos.

## <a name="feature-capability-comparison"></a>Comparação entre capacidades

Esta tabela apresenta uma comparação entre as capacidades do Power Automate e dos fluxos de trabalho clássicos. 

*Estamos a adicionar continuamente novas capacidades ao Power Automate, para que se encontre a par e ainda melhor do que as capacidades clássicas de fluxo de trabalho clássico. Atualizaremos as informações desta tabela como ganhos de capacidades do Power Automate; volte a verificar com frequência! Para obter informações sobre capacidades de fluxo futuras que o ajudarão a substituir o fluxo de trabalho clássico com fluxo, consulte [Novidades e planos para o Power Automate](https://docs.microsoft.com/business-applications-release-notes/April19/microsoft-flow/planned-features) nas Notas de Versão de abril de 2019!*

<table>
<tr>
<th colspan="2">Funcionalidade</th>
<th>Power Automate</th>
<th>Fluxo de trabalho clássico</th>
</tr>
<tr>
<td rowspan="5">Modelação</td>
<td>Ramificação condicional</td>
<td>Sim</td>
<td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar ciclos
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Condições de espera em campos
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ramo paralelo
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Conectores de configuração inicial para sistemas externos (ações de acionador e execução em serviços externos)
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Composição
                    
                </td>
                <td>
                    
   Conteúdo dinâmico
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Acesso à pré-imagem de dados do evento
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar fluxos de trabalho subordinados
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar ações do Common Data Service (incluindo personalizadas)
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar atividades de fluxos de trabalho personalizados
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Agrupar passos para executar numa transação
                    
                </td>
                <td>
                    
   Sim (conjuntos de alterações)
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Fluxos de trabalho de aprovação
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Execução
                    
                </td>
                <td>
                    
   Acionar ao alterar os campos
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Acionar condicionalmente em valores de campo (por exemplo, em determinada data, num campo de data)
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Acionar em vários eventos de entidades do Common Data Service
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar a pedido
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Âmbitos executar como    <br/>
   (por exemplo, organização, unidade de negócios, utilizador)
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar com base num agendamento
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar de forma síncrona (em tempo real)
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td rowspan="2">
                    
   Histórico
                    
                </td>
                <td>
                    
   Auditoria
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Análise de execução
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td rowspan="3">
                    
   Criação e portabilidade
                    
                </td>
                <td>
                    
   Suporte da solução
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Estruturador moderno
                    
                </td>
                <td>
                    
   Sim
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
<td>Criação assistida por IA</td>
<td>Sim</td>
<td>No</td>
</tr>
</table>

## <a name="example-scenario-replace-workflow-with-a-flow"></a>Cenário de exemplo: substituir o fluxo de trabalho por um fluxo

Imagine um cenário de vendas em que elaborou uma proposta para um cliente e agora precisa de solicitar a aprovação da equipa de gestão antes de enviar a proposta ao cliente. Com os fluxos de trabalho clássicos, tal não seria fácil, e a maioria das soluções para esse efeito requer que um programador escreva atividades de fluxo de trabalho personalizadas para recuperar os itens de linha da proposta.

Com os fluxos, isso será mais fácil de criar, conforme será demonstrado nas instruções mais à frente que incluem algumas das capacidades do Power Automate para apoiar este cenário. Isto inclui:

-   Criar um fluxo executado a pedido

-   Obter uma lista de registos relacionados com uma entidade do Common Data Service

-   Executar ciclos através de uma lista de registos

-   Enviar pedidos de aprovação

Para permitir que uma pessoa de vendas acione o pedido de aprovação a pedido:

1. Inicie sessão no [Power Automate](https://flow.microsoft.com/) e crie um fluxo numa solução. Mais informações: [Criar um fluxo numa solução](create-flow-solution.md). 

1. Na lista de acionadores, selecione **Common Data Service (Ambiente Atual) – Quando um registo está selecionado** e selecione **Propostas** como entidade. Este acionar permite que um fluxo seja executado a pedido num registo ou numa lista de registos.

1. Com o acionador configurado, adicione as ações a executar no nosso fluxo. Tal irá fornecer ao aprovador um resumo dos detalhes de que necessita para identificar os itens e valores propostos. Comece por adicionar a ação **Common Data Service (Ambiente Atual) – Lista de registos**. Uma vez que queremos obter itens de linha individuais de uma Proposta, defina a entidade como **Linhas de proposta**. Para garantir que listamos apenas os itens de linha da proposta que pertencem à Proposta para a qual o fluxo foi acionado, vamos especificar um critério de filtro de estilo OData. No campo **Filtrar Consulta**, escreva *\_quoteid_value eq* e, em seguida, selecione *Proposta* na lista de valores dinâmicos apresentados.

    ![Definir o fluxo](media/define-flow-1.png "Definir o fluxo")

1. Uma vez que queremos resumir os itens de linha da proposta para aprovação, adicione a ação **Inicializar variável**. Defina o campo **Nome** como *Resumo da linha de proposta* e o **Tipo** como Cadeia (no menu pendente) e deixe o campo **Valor** vazio.

1. Adicione a ação **Anexar a variável de cadeia** e, em seguida, selecione a variável *Resumo da linha de proposta* que criámos anteriormente. No campo **Valor**, selecione *Quantidade, Nome, Preço por unidade, Montante alargado e Montante manual* na lista de valores dinâmicos. O estruturador do Power Automate identifica que estes valores são da lista de itens de linha da proposta e adiciona esta ação num ciclo **Aplicar a cada** para garantir que as informações de cada uma das linhas são adicionadas a este resumo.

    ![Definir o fluxo](media/define-flow-2.png "Definir o fluxo")

1. Para pedir a aprovação do resumo da proposta que criámos, adicione a ação **Aprovação – Iniciar e aguardar aprovação**. Selecione um tipo de Aprovação (por exemplo, Aprovar/Rejeitar – Primeiro a responder), atribua um **Título** ao Pedido de aprovação (por exemplo, o Nome da Proposta para a qual está a ser solicitada aprovação, a selecionar na lista de valores dinâmicos) e introduza o endereço de e-mail da pessoa que tem de rever e aprovar a proposta no campo **Atribuído a**. No campo Detalhes, adicione a variável *Resumo de linha da proposta*, juntamente com quaisquer outras informações que possam ser relevantes, com o selecionador de valor dinâmico (por exemplo, Montante Total).

1. Para determinar o que acontece assim que uma aprovação é aceite ou rejeitada, adicione a ação **Condição**. Selecione *Resultado* na lista de valores dinâmicos no primeiro campo na condição, *Contém* no menu pendente no segundo campo e introduza *Aceitar* no terceiro campo da condição. Por fim, adicione ações com base no resultado da aprovação (por exemplo, enviar um e-mail de notificação).

    ![Definir o fluxo](media/define-flow-3.png "Definir o fluxo")

Agora temos a estrutura de aprovação criada para que o aprovador tenha todas as informações necessárias para tomar uma decisão sobre os próximos passos. Segue-se o exemplo completo do fluxo a pedido para pedir aprovação:

![Estrutura do fluxo de aprovação](media/approval-flow-structure.png "Estrutura do fluxo de aprovação")

Quando executa este fluxo com a proposta, este resume os itens de linha dessa proposta e envia um pedido de aprovação ao qual o aprovador pode responder a partir no Power Automate ou a partir do e-mail acionável que recebe. Segue-se um exemplo do ecrã:

![Fluxo em ação](media/flow-in-action.png "Fluxo em ação")

## <a name="recommended-patterns"></a>Padrões recomendados


-   **Fluxos de trabalho com lógica condicional else-if complexa**  
    
    Em vez de utilizar condições, recomendamos a utilização da [ação de comutador](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-switch-statement#add-switch-statement).

-   **Fluxos de trabalho que são executados através do plug-in/código**  
    
    É recomendável reestruturar o fluxo para começar com os acionadores.

    -   Utilize acionadores do Common Data Service para executar fluxos com base em eventos.

    -   Para executar fluxos com base em eventos num serviço externo, utilize mais de 260 conectores de configuração inicial.

    -   Em cenários em que um conector de que precisa não esteja pronto a utilizar, crie facilmente o seu próprio conector personalizado. Veja [Aprender a criar conectores personalizados](https://docs.microsoft.com/connectors/custom-connectors/define-blank).

    -   Por fim, se houver cenários em que não pode acionar o fluxo através do conector do Common Data Service, utilize um dos conectores prontos a utilizar, crie um conector personalizado ou tire partido do [acionador Quando um pedido HTTP é recebido](https://docs.microsoft.com/azure/connectors/connectors-native-reqres#use-the-http-request-trigger) para invocar o fluxo

-   **Fluxos de trabalho que são executados de forma recursiva**  
    
    Em vez disso, utilize o ciclo [do-until](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) ou [aplicar a cada](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#foreach-loop) nos Fluxos

-   **Fluxos de trabalho que precisam de uma lista de registos**  
    
    Utilize a ação **listar registos**. Ao utilizar esta ação, defina os critérios de filtragem de registos com a sintaxe do OData para otimizar a ação e minimizar o número de registos que deseja obter.

-   **Fluxos de trabalho que estão em suspensão para serem executados com base num agendamento**  
    
    Utilize o acionador de **recorrência** para executar a lógica de negócio em intervalos periódicos.

-   **Fluxos de trabalho para os quais as execuções foram geridas para garantir que as atividades fossem executadas numa única transação**  
    
    Utilize a [ação conjunto de alterações](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/automated-flows-support-change-sets-common-data-service) para garantir que todas as ações dentro do mesmo são executadas como uma única unidade atómica na qual todas são bem-sucedidas ou todas falham enquanto grupo. Se alguma das ações num conjunto de alterações falhar, as alterações feitas pelas operações concluídas serão revertidas.

-   **Monitorizar a existência de falhas nas execuções de fluxos de trabalho**  
    
    No Power Automate, utilize a **definição executar após** numa ação para a configurar para ser executada quando a ação anterior falhar. Por exemplo, enviar uma notificação móvel do Power Automate quando a ação **atualizar um registo** falhar ou expirar.

## <a name="faqs"></a>FAQs


-   **Tenho uma licença do Dynamics 365. Posso utilizar o Power Automate?**

    Todos os utilizadores do Dynamics 365 têm o direito de utilizar o Power Automate. Veja as nossas informações de licenciamento: <https://flow.microsoft.com/pricing/>

-   **Com que frequência os meus fluxos podem ser acionados?**

    -   Os fluxos do Dynamics 365 (ou do Common Data Service) são executados em tempo quase real depois do acionador porque utilizam webhooks (não são necessárias consultas)

    -   Assim como acontece com o acesso direto à API, existem limitações/limites no sistema, totalmente documentados aqui: <https://docs.microsoft.com/flow/limits-and-config>

    -   Especificamente, existe um limite de 100 mil ações por 5 minutos, por fluxo – e um único ciclo num fluxo não pode processar mais de 100 mil itens ao mesmo tempo

    -   Máximo de 6 GB de débito por 5 minutos

-   **Durante quanto tempo pode um único fluxo ser executado?**  
    
    A execução de um fluxo único atinge o tempo limite após 30 dias.

-   **Como mover os meus fluxos entre ambientes?**  
    
    À semelhança dos fluxos de trabalho clássicos, pode criar fluxos em soluções para suportar o ciclo de vida completo da aplicação para processos.

-   **As dependências do Power Automate são monitorizadas no Common Data Service?**  
    
    À semelhança de outros componentes numa solução, todas as dependências de fluxos em soluções são controladas no Common Data Service.

-   **E quanto aos fluxos de trabalho síncronos?** 
 
    Deve reavaliar a necessidade de fluxos de trabalho síncronos para identificar se o objetivo, ou partes do fluxo de trabalho, podem ser criados com um fluxo. Em particular, vemos a partir da nossa telemetria que os fluxos de trabalho síncronos são um contribuidor significativo para uma má experiência de desempenho geral do utilizador final. Para muitas utilizações, contudo, será preferível dividir estas ações como assíncronas para que o utilizador possa continuar com a atividade enquanto o Power Automate continua a garantir a conclusão da ação.

-   **Com o Power Automate, os meus dados irão permanecer na região (ou seja, na mesma região que o meu ambiente de Dynamics 365 ou Common Data Service)?**  
    
    Sim, o Power Automate utiliza sempre a mesma região do Common Data Service.

-   **É necessário fazer alterações no proxy ou na firewall?**  
    
    Veja a [referência de configuração do endereço IP](limits-and-config.md#ip-address-configuration) para determinar se precisa de fazer alterações no proxy ou na firewall.
