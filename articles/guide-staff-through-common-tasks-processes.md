---
title: Criar a lógica empresarial de negócio através de processos com o Power Apps | MicrosoftDocs
description: Obter informações sobre os diferentes tipos de lógica de negócio que pode utilizar na aplicação
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: 0b4e6602-5701-4859-81cc-6f6fe50901b2
caps.latest.revision: 44
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: af51cc703dbb42296493237bdd25387c6c15720c
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298116"
---
# <a name="create-custom-business-logic-through-processes"></a>Criar lógica empresarial personalizada através de processos


Definir e impor processos de negócio consistentes é uma das principais razões pelas quais as pessoas utilizam aplicações orientadas por modelos. Os processos consistentes ajudam a garantir que as pessoas que utilizam o sistema podem concentrar-se no trabalho e não a recordar-se de que têm de efetuar um conjunto de passos manuais. Os processos podem ser simples ou complexos e podem mudar ao longo do tempo.  
  
O Power Apps inclui vários tipos de processos, cada um concebido para uma finalidade diferente:  
  
-   Fluxos do processo de negócio  
  
-   Fluxos de tarefas móveis  
  
-   Fluxos de Trabalho  
  
-   Ações  
  
 Semelhante aos processos, também pode criar recomendações e regras de negócio. Para obter mais informações, veja [Criar regras de negócio e recomendações para aplicar a lógica num formulário](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form)  

> [!NOTE]
>  A utilização de processos pode afetar os requisitos de licença para o Power Apps e fluxos. Para obter mais informações, veja [Requisitos de licença para entidades](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Quando utilizar fluxos do processo de negócio  
 Utilize um fluxo do processo de negócio quando pretender que o pessoal passe pelas mesmas fases e siga os mesmos passos para interagir com um cliente. Por exemplo, utilize um fluxo do processo de negócio se pretende que todos processem os pedidos do suporte ao cliente da mesma forma, ou para solicitar ao pessoal a aprovação de uma factura antes de submeter uma encomenda.  
  
 O ambiente inclui vários fluxos de processo de negócio prontos a utilizar para tarefas comuns de vendas, serviço e marketing, que pode utilizar com poucas ou nenhumas alterações. Também pode criar o seu próprio fluxo. Veja o seguinte tópico para obter mais informações sobre fluxos de processos de negócio:  
  
-   [Criar um fluxo de processo de negócio](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Quando utilizar fluxos de trabalho  
 Utilize fluxos de trabalho para automatizar os processos de negócio nos bastidores. Os fluxos de trabalho são normalmente iniciados por eventos de sistema para que o utilizador não tenha de estar consciente de que estão ser a executados. Os fluxos de trabalho que funcionam em segundo plano são “assíncronos”. Os fluxos de trabalho também podem ser configurados para serem iniciados manualmente pelas pessoas. quando pretende automatizar tarefas comuns, tais como o envio automático de uma mensagem de e-mail de confirmação ao cliente quando a encomenda é expedida. Os fluxos de trabalho que funcionam em tempo real são “síncronos”. Para mais informações sobre fluxos de trabalho, consulte [Processos de fluxo de trabalho](workflow-processes.md)  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Quando utilizar as Ações  
 Utilize as Ações quando pretender automatizar uma série de comandos no sistema. As Ações expandem o vocabulário disponível para os programadores para expressar processos de negócio. Com verbos principal como criar, atualizar, eliminar, atribuir e fornecido pelo sistema, de uma ação sua verbos os principais criar um verbos mais expressivos como aprovar, escalam, encaminhar, ou programam. Se a definição de um processo de negócio sofrer alterações, uma pessoa que não seja um programador pode editar a ação para que o código não tem de ser alterado.  Para obter mais informações sobre Ações, veja [Ações](create-actions.md)  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-power-automate"></a>Quando utilizar o Power Automate  
 Utilize o Power Automate quando necessitar de criar fluxos de trabalho automatizados para efetuar ações entre o seu ambiente e as suas aplicações e serviços favoritos, como o Dynamics 365, Twitter, Dropbox, serviços Google, Office 365 e SharePoint. Pode acionar um fluxo com base numa ação específica ou invocar a partir da sua aplicação. Mais informações: [Utilizar o Power Automate  para automatizar processos em serviços](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>Onde posso criar processos?  
 Existem dois caminhos para navegar até aos processos:  
  
- Abra o [explorador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e aceda a **Componentes > Processos.** Este caminho fornece acesso conveniente quando estiver a realizar outro trabalho de personalização nas ferramentas de personalização.  

- **[Definições](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Processos.** Este caminho permite-lhe utilizar as vistas definidas para a entidade Processo, incluindo as vistas personalizadas.  
  
 Fluxos de processo de negócio individuais também podem ser editados utilizando **Editar processo** do botão na barra de comandos para o formulário onde o fluxo de processos de negócio está ativo.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>Quem pode criar processos?  
 Apenas as pessoas com a função de segurança de Administrador do Sistema, Personalizador de Sistema ou CEO – Gestor Empresarial podem criar processos que se apliquem a todo o ambiente. As pessoas com outros direitos de acesso podem criar processos com nível de acesso limitado. Por exemplo, utilizadores com o nível de acesso de utilizador podem criar fluxos de trabalho para utilização com os registos que possui.  
  
 A tabela seguinte mostra o nível de acesso de processos com base no direito de acesso.  
  
|||  
|-|-|  
|**Direito de acesso**|**Nível de acesso**|  
|CEO - Gestor Empresarial|Organização|  
|Administrador de Sistema|Organização|  
|Personalizador de Sistemas|Organização|  
|Vice-presidente de Marketing|Nível Principal: Unidades de Negócio Subordinadas|  
|Vice-Presidente de Vendas|Nível Principal: Unidades de Negócio Subordinadas|  
|Gestor de Serviços do |Unidade de Negócio|  
|Gestor de Marketing|Unidade de Negócio|  
|Gestor de Vendas|Unidade de Negócio|  
|Gestor da Agenda|Unidade de Negócio|  
|Representante de Suporte ao Cliente|Utilizador|  
|Profissional de Marketing|Utilizador|  
|Representante de Vendas|Utilizador|  
|Agendador|Utilizador|  
  
> [!NOTE]
>  Quando os utilizadores possam ter a criar o fluxo de processos empresariais, o fluxo de trabalho em tempo real, ou os processos de ação, necessitarão de ter privilégios de **Ativar fluxos de processos de negócio** ou de **Ativar processos de tempo real** utilizar.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Mais informações sobre fluxos de trabalho e Ações  
 Os processos podem condições de verificação, para aplicar a lógica de ramificação, e para executar ações. Com estas ações numa série de passos. A tabela seguinte descreve os passos no fluxo de trabalho e nos processos de ação. Para mais detalhes consulte os tópicos para cada tipo de processo.  
  
|Passo|Tipo de processo|Descrição|  
|----------|------------------|-----------------|  
|**Fase**|Fluxo de Trabalho, Ação|As fases de trabalho facilitam a leitura da lógica de fluxo de trabalho e explicam a lógica de fluxo de trabalho. No entanto, as fases não afectam a lógica nem o comportamento dos fluxos de trabalho. Se um processo tiver fases, quaisquer passos do processo têm de estar contidos numa fase.|  
|**Condição de Verificação**|Fluxo de Trabalho, Ação|Uma declaração lógica "if-\<condition> then".<br /><br /> Poderá verificar os valores do registo no qual fluxo de trabalho está em execução, quaisquer registos associados a esse registo numa relação N:1 ou quaisquer registos criado por passos anteriores. Com base nestes valores pode definir passos adicionais quando a condição é `true`.|  
|**Ramo Condicional**|Fluxo de Trabalho, Ação|Uma declaração “else-if-then " lógica, o editor utiliza o texto “Otherwise, if \<condition> then:”<br /><br /> Selecione uma condição de verificação definida anteriormente e poderá adicionar um ramo condicional para definir passos adicionais quando a condição de verificação devolve `false`.|  
|**Ação Predefinida**|Fluxo de Trabalho, Ação|Uma declaração "else" lógica. o editor utiliza texto “Caso contrário:”<br /><br /> Selecione uma condição de verificação, ramo condicional, condição de espera ou ramo de espera paralelo definido anteriormente e pode utilizar uma ação predefinida para definir passos para todos os casos que não correspondem aos critérios definidos nos elementos de condição ou de ramo.|  
|**Condição de Espera**|Fluxo de trabalho só em segundo plano|Permite que um fluxo de trabalho de segundo plano seja interrompido até os critérios definidos pela condição serem correspondidos. O fluxo de trabalho recomeça automaticamente quando os critérios especificados na condição de espera tiverem sido cumpridos.|  
|**Ramo de Espera Paralelo**|Fluxo de trabalho só em segundo plano|Define uma condição de espera alternativa para um fluxo de trabalho de segundo plano com um conjunto correspondente de passos adicionais que só são executados quando o critério inicial é satisfeito. Pode utilizar ramos de espera paralelos para criar limites de tempo na lógica de fluxo de trabalho. Estes ajudam a impedir que o fluxo de trabalho aguarde indefinidamente até que os critérios definidos numa condição de espera tenham sido cumpridos.|  
|**Atribuir Valor**|Ação|Predefinir um valor para um parâmetro de saída variável ou do processo.|  
|**Criar Registo**|Fluxo de Trabalho, Ação|Cria um novo registo para uma entidade e atribui valores a atributos.|  
|**Atualizar Registo**|Fluxo de Trabalho, Ação|Poderá atualizar o registo no qual fluxo de trabalho está em execução, quaisquer registos associados a esse registo numa relação N:1 ou quaisquer registos criado por passos anteriores.|  
|**Atribuir Registo**|Fluxo de Trabalho, Ação|Poderá atribuir o registo no qual fluxo de trabalho está em execução, quaisquer registos associados a esse registo numa relação N:1 ou quaisquer registos criado por passos anteriores.|  
|**Enviar E-mail**|Fluxo de Trabalho, Ação|Envia uma mensagem de correio eletrónico. Pode optar por criar uma mensagem de correio eletrónico nova ou utilizar um modelo de correio eletrónico configurado para a entidade do registo em que o fluxo de trabalho está em executar, quaisquer entidades que tenham uma relação N:1 relação com a entidade ou a entidade para quaisquer registos criados por passos anteriores.|  
|**Iniciar Fluxo de Trabalho Subordinado**|Fluxo de Trabalho, Ação|Inicia um processo de fluxo de trabalho configurado como um fluxo de trabalho subordinado.|  
|**Alterar Estado**|Fluxo de Trabalho, Ação|Altera o estado do registo no qual processo está em execução, quaisquer registos associados a esse registo numa relação N:1 ou quaisquer registos criado por passos anteriores.|  
|**Parar Fluxo de Trabalho**|Fluxo de Trabalho, Ação|Para o fluxo de trabalho ou a ação. Pode definir o estado de **Com êxito** ou de **Cancelado** e especificar uma mensagem de estado.|  
|**Passo Personalizado**|Fluxo de Trabalho, Ação|Fornece extensões aos elementos lógicos disponíveis por predefinição. Os passos podem incluir condições, acções, outros passos ou uma combinação destes elementos. Os programadores podem criar passos de fluxo de trabalho personalizados. Por predefinição, não existem passos personalizados disponíveis.|

  

