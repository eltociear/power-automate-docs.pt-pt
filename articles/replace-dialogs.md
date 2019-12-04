---
title: Substituir diálogos por processos do fluxo de negócio ou aplicações baseadas em telas | Microsoft Docs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- flow
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b338991cfdbb73a8a0464fd4322714ece82c2ac5
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74373027"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>Substituir diálogos por processos do fluxo de negócio ou aplicações baseadas em telas
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Os [diálogos foram preteridos](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated) e devem ser substituídos por fluxos de processo de negócio ou aplicações baseadas em telas. Este tópico descreve as diferentes capacidades destas opções, bem como situações em que um fluxo de processo de negócio ou uma aplicação baseada em telas incorporados num formulário controlado por modelos podem ser utilizados para substituir um diálogo existente.

## <a name="feature-capability-comparison"></a>Comparação entre capacidades

Esta tabela lista o conjunto de capacidades dos diálogos e as capacidades equivalentes dos fluxos de processo de negócio e aplicações baseadas em telas.


|Capacidade dos diálogos  | Capacidade em termos de fluxos de processo de negócio?  | Capacidade em termos de aplicações baseadas em telas?  |
|---------|---------|---------|
|Página     | Sim <br/> (fase do processo de negócio)    | Sim <br/> (ecrã da aplicação)        |
|Apenas pedido   |  Não    |  Sim <br/> (etiquetas)        |
|Pedido e resposta     |  Sim <br/> (apenas atributos de entidade)    | Sim <br/> (etiquetas e campos de texto)    |
|Argumentos de entrada     |  Limitado <br/> (passos na fase do processo de negócio)    | Sim <br/> (parâmetros de cadeia de consulta)     |
|Variáveis   |  Não     |  Sim       |
|Variáveis de consulta    |  Não     |  Sim     |
|Lógica de ramificação condicional    |  Sim     | Sim <br/>  (navegar para qualquer ecrã na aplicação)    |
|Reutilizar <br/> (iniciar como um diálogo subordinado)   |  Não     | Sim <br/> (navegar para qualquer ecrã na aplicação, iniciar outra aplicação numa nova janela)     |
|Executar fluxos de trabalho no início/fim    |   Sim      |  Não <br/> (utilizar um fluxo como alternativa)  |
|Executar fluxos de trabalho na entrada    | Sim    | Não <br/> (utilizar um fluxo como alternativa)   |
|Executar fluxos de trabalho na transição de página   |  Sim       | Não <br/> (utilizar um fluxo como alternativa)    |
|Começar a utilizar um URL  |   Não      |  Sim     |
|Iniciar sessão    |  Sim       |  Não     |
|Suporte de SKDs   |  Sim     |  Sim     |

### <a name="additional-capabilities-with-business-process-flows"></a>Capacidades adicionais com fluxos de processo de negócio
- Análises do processo (visualizações, gráficos e tempo despendido numa fase)
- Controlos personalizados

### <a name="additional-capabilities-with-canvas-apps"></a>Capacidades adicionais com aplicações baseadas em telas
- Análises da aplicação (utilização e desempenho da aplicação)
- Composição da página de várias entidades
- Executar fluxos
- Conectores de dados (padrão e personalizados)
- Iniciar como uma aplicação autónoma
- Esquema configurável

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>Escolher entre um fluxo de processo de negócio e aplicações baseadas em telas
Ao escolher a substituição do diálogo, é importante considerar a experiência que pretende proporcionar ao utilizador. Tenha também em atenção que praticamente qualquer diálogo pode ser modelado com uma aplicação baseada em telas.

Os fluxos de processo de negócio são mais indicados para substituir diálogos que modelam processos que fornecem orientações a um grupo de trabalho abrangente que, por sua vez, requer a colaboração de grupos de utilizadores e o contexto da aplicação do Dynamics 365. Por exemplo, a revisão e o encaminhamento da proposta. 

Em alternativa, as aplicações baseadas em telas podem ser utilizadas para substituir diálogos que modelam tarefas prescritivas, tais como um script telefónico para oportunidades potenciais, ou para simplificar a experiência do utilizador em relação a outras tarefas, tais como a atualização de uma oportunidade. Tenha em atenção que estes cenários podem ainda beneficiar da existência de uma aplicação baseada em telas autónoma. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>Substituição de diálogos através do cenário de fluxo de processo de negócio
Imagine que tem um diálogo que, ao longo de uma série de páginas, solicita informações fundamentais ao utilizador, gera uma proposta, envia um e-mail para os revisores aceitarem ou rejeitarem a proposta, antes do envio da proposta para o cliente. Este tipo de processo é modelado com mais eficácia através de um fluxo de processo de negócio. 

Para substituir o diálogo, comece por identificar as principais fases no processo. Estas poderão incluir o seguinte: fase *Preparar Conteúdo* para garantir que todos os produtos estão listados e são aplicados descontos, fase *Gerar Proposta* para criar a proposta e revê-la em termos de precisão do formato, fase *Revisão Principal* para enviar a proposta para revisão e aprovação, fase *Revisão Secundária* para rever a proposta em determinadas circunstâncias e uma fase *Fornecer Proposta* para enviar a proposta ao cliente.

Em seguida, identifique os principais passos que os utilizadores têm de seguir no processo. Por exemplo, a fase *Preparar Conteúdo* poderá conter um passo simples de verdadeiro ou falso para que o utilizador volte a verificar os produtos incluídos na proposta, um passo de pesquisa obrigatório para selecionar uma lista de preços e um passo numérico para introduzir um desconto antes de passar para a fase seguinte. A fase *Gerar Proposta* poderá ter um [passo de ação](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow) para criar uma proposta baseada em todas as informações recolhidas anteriormente na fase *Preparar Conteúdo* e o seu registo associado ao Dynamics 365. As fases *Revisão Principal* e *Revisão Secundária* poderão ter vários passos de verdadeiro ou falso para orientar a revisão da proposta, juntamente com um passo necessário para registar o estado de aprovação, e garantir que o processo só pode passar para a fase seguinte após a receção da aprovação. Configure a [segurança de nível de campo](/customer-engagement/admin/field-level-security) neste passo para se certificar de que apenas os revisores autorizados podem aprovar a proposta.  Para além disso, é possível adicionar um fluxo de trabalho às fases *Revisão Principal* e *Revisão Secundária* de modo que, à entrada, seja enviado um e-mail de notificação para todos os revisores. 

Por fim, configure as fases e os passos do fluxo de processo de negócio, juntamente com a lógica condicional, para orientar o fluxo de processo. Neste exemplo, poderá adicionar um [ramo condicional](enhance-business-process-flows-branching.md) após a fase *Revisão Principal* de forma que, se um passo exigir um segundo nível de revisão, a fase seguinte no processo seja a fase *Revisão Secundária*. Caso contrário, será a fase *Fornecer Proposta*.

Para disponibilizar este fluxo de processo de negócio aos utilizadores, certifique-se de que os utilizadores certos têm privilégios para o fluxo de processo de negócio e o ativam depois.

Para obter mais informações sobre como criar um fluxo de processo de negócio, veja [Tutorial: criar um fluxo de processo de negócio para normalizar processos](create-business-process-flow.md).

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Substituição de diálogos através de um cenário com uma aplicação baseada em telas

Imagine que tem um diálogo, que segue um script telefónico que orienta os representantes de vendas para falarem com oportunidades potenciais de vendas através de chamadas não solicitadas. Este processo pode ser facilmente registado através de uma aplicação baseada em telas.

Comece por ligar às origens de dados cujos dados terá de ler e escrever. Neste exemplo, é utilizada uma [ligação ao Dynamics 365](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) para obter informações sobre oportunidades potenciais, contas e contactos.

Comece por identificar o número de ecrãs necessários. Neste exemplo, poderá optar por ter cinco ecrãs. 
-   Ecrã 1. Para selecionar uma oportunidade potencial a partir de uma lista a contactar.
-   Ecrã 2. Para apresentações, verificação de disponibilidade para uma conversa e agendamento de uma chamada de retorno numa data posterior. 
-   Ecrã 3. Para determinar o BANT (orçamento, autoridade, necessidade e linha cronológica). 
-   Ecrã 4. Para registar os passos seguintes e agendar chamadas de seguimento. 
-   Ecrã 5. No final da chamada, agradecer à oportunidade potencial pelo tempo despendido.

Em seguida, compile cada um dos ecrãs. No primeiro ecrã, [compile uma galeria](/powerapps/maker/canvas-apps/customize-layout-sharepoint) de oportunidades potenciais para as quais se tem de efetuar uma chamada. No segundo, utilize etiquetas para dar um título ao ecrã e forneça o script telefónico, enquanto utiliza controlos como os botões de opção para averiguar se é uma boa altura para a pessoa falar. Se for, utilize a lógica condicional para ativar um botão para navegar para o ecrã seguinte; se não for, exponha um script no mesmo ecrã para tentar agendar uma chamada de retorno com o cliente. Da mesma forma, defina o seu script telefónico nos ecrãs subsequentes.

Por fim, [defina a navegação pelos ecrãs](/powerapps/maker/canvas-apps/functions/function-navigate). Neste exemplo, para além de navegar pelos ecrãs sequencialmente, pode encaminhar o utilizador do segundo ecrã para o último (o fim do script a agradecer à oportunidade potencial pelo tempo despendido) se a oportunidade potencial não estiver interessada em manter uma conversa.

Para disponibilizar esta aplicação aos utilizadores, publique a aplicação. Pense na forma como a disponibilização de uma aplicação autónoma que fornece scripts telefónicos e suporta a introdução rápida de dados poderia transformar um cenário semelhante a este.

Imagine que quer incorporar esta experiência no Dynamics 365 for Sales. Para o fazer, comece por criar um iframe num formulário do Dynamics 365 for Sales. Em seguida, navegue para a secção **Aplicações** no menu do Power Apps, selecione a aplicação que acabou de publicar, copie a ligação Web por baixo do separador **Detalhes** e cole-a como o URL do iframe. 

Se pensarmos mais além, imaginemos que pretendia que esta aplicação ficasse logo disponível no formulário principal da oportunidade potencial e que estivesse no contexto da oportunidade potencial para que não exigisse que o utilizador selecionasse uma oportunidade potencial no primeiro ecrã. Para transmitir informações relevantes para a aplicação, modifique o URL do iframe para acrescentar uma cadeia de consulta que contenha estas informações, como os IDs da oportunidade potencial ou da conta, através do JavaScript que é executado num determinado evento, tal como no carregamento do formulário. Em seguida, atualize a aplicação para remover o primeiro ecrã (para a seleção da oportunidade potencial) e aceda, em alternativa, aos valores transmitidos para a aplicação através da cadeia de consulta com a [função Param](/powerapps/maker/canvas-apps/functions/function-param).

## <a name="dialog-replacement-faq"></a>FAQ sobre a substituição de diálogos

As dependências das aplicações baseadas em telas são controladas? 
- As dependências das aplicações de tela são controladas da mesma forma que as dependências nas aplicações do Dynamics 365.

Posso iniciar uma aplicação baseada em telas como um item de pop-up a partir de um botão na barra de comando?
- Sim. Para tal, basta definir o URL de destino para o URL da aplicação baseada em telas, obtido a partir da secção **Detalhes** da aplicação conforme descrito anteriormente.

Os fluxos de trabalho podem ser chamados a partir de uma aplicação baseada em telas?
- Esta ação não é suportada. Como alternativa, recomendamos que utilize um fluxo. Mais informações: [Introdução aos fluxos de botões com entradas de utilizador](button-flow-with-user-input-tokens.md)

Posso converter automaticamente diálogos em fluxos de processo de negócio ou aplicações baseadas em telas?
- Não existe uma forma automatizada para converter diálogos em fluxos de processo de negócio ou aplicações baseadas em telas.


## <a name="see-also"></a>Veja também
[Tutorial: criar um fluxo de processo de negócio para normalizar processos](create-business-process-flow.md) </br>
[O que são aplicações de tela no Power Apps?](/powerapps/maker/canvas-apps/getting-started)


