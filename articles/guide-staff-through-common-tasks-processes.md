---
title: Criar lógica de negócio personalizada através de processos com o Power Apps | Microsoft Docs
description: Saiba mais sobre os diferentes tipos de lógica de negócio que pode utilizar na sua aplicação
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
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194744"
---
# <a name="create-custom-business-logic-through-processes"></a>Criar lógica de negócio personalizada através de processos


Definir e impor processos de negócio consistentes é um dos principais motivos pelos quais as pessoas utilizam aplicações baseadas em modelos. Os processos consistentes ajudam a garantir que as pessoas que utilizam o sistema podem focar-se no seu trabalho e não em lembrarem-se de executar um conjunto de passos manuais. Os processos podem ser simples ou complexos e podem sofrer alterações ao longo do tempo.  
  
O Power Apps inclui vários tipos de processos, cada um estruturado para um propósito diferente:  
  
-   Fluxos de processo de negócio  
  
-   Fluxos de tarefas móveis  
  
-   Fluxos de Trabalho  
  
-   Ações  
  
 Assim como os processos, também pode criar regras de negócio e recomendações. Para obter mais informações, veja [Criar regras de negócio e recomendações para aplicar a lógica num formulário](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form)  

> [!NOTE]
>  A utilização de processos pode afetar os requisitos de licença do Power Apps e dos fluxos. Para obter mais informações, veja [Requisitos de licença para entidades](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Quando utilizar fluxos de processo de negócio  
 Utilize um fluxo de processo de negócio quando quiser que a equipa percorra as mesmas etapas e siga os mesmos passos para interagir com um cliente. Por exemplo, utilize um fluxo de processo de negócio se quiser que todas as pessoas lidem com os pedidos de serviço de cliente da mesma forma ou para exigir que a equipa obtenha aprovação para uma fatura antes de submeter uma encomenda.  
  
 O ambiente inclui vários fluxos de processo de negócio prontos a utilizar para tarefas comuns de vendas, serviço e marketing, que pode utilizar com poucas ou nenhumas alterações. Também pode criar o seu próprio fluxo. Veja o seguinte tópico para obter mais informações sobre fluxos de processos de negócio:  
  
-   [Criar um fluxo de processo de negócio](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Quando utilizar fluxos de trabalho  
 Utilize fluxos de trabalho para automatizar os processos de negócio nos bastidores. Os fluxos de trabalho são normalmente iniciados por eventos de sistema para que o utilizador não precise de estar ciente de que estão em execução. Os fluxos de trabalho que funcionam em segundo plano são "assíncronos". Os fluxos de trabalho também podem ser configurados para que as pessoas os possam iniciar manualmente. Quando quer automatizar tarefas comuns, como enviar automaticamente um e-mail de confirmação para um cliente, quando uma encomenda é expedida. Os fluxos de trabalho que funcionam em tempo real são "síncronos". Para obter mais informações sobre fluxos de trabalho, veja [Processos de fluxo de trabalho](workflow-processes.md).  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Quando utilizar Ações  
 Utilize Ações quando quiser automatizar uma série de comandos no sistema. As ações expandem o vocabulário disponível para os programadores expressarem os processos de negócios. Os verbos principais, como Criar, Atualizar, Eliminar e Atribuir, são fornecidos pelo sistema. Uma Ação utiliza esses verbos principais para criar verbos mais expressivos, como Aprovar, Escalar, Encaminhar ou Agendar. Se a definição de um processo de negócio mudar, alguém que não seja um programador pode editar a Ação para que o código não tenha de ser alterado.  Para obter mais informações sobre Ações, veja [Ações](create-actions.md)  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-power-automate"></a>Quando utilizar o Power Automate  
 Utilize o Power Automate quando precisar de criar fluxos de trabalho automatizados para executar ações entre o ambiente e o serviço ou a aplicação preferencial, como Dynamics 365, Twitter, Dropbox, serviços Google, Office 365 e SharePoint. Pode acionar um fluxo com base numa ação específica ou invocar a partir da sua aplicação. Mais informações: [Utilizar o Power Automate para automatizar os processos em serviços](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>Onde posso criar processos?  
 Existem dois caminhos para navegar até aos processos:  
  
- Abra o [explorador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e aceda a **Componentes > Processos.** Este caminho fornece acesso conveniente quando estiver a realizar outro trabalho de personalização nas ferramentas de personalização.  

- **[Definições](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Processos.** Este caminho permite-lhe utilizar as vistas definidas para a entidade Processo, incluindo as vistas personalizadas.  
  
 Os fluxos de processos de negócio individuais também podem ser editados com o botão **Editar Processo** na barra de comandos para o formulário no qual o fluxo do processo de negócio está ativo.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>Quem pode criar processos?  
 Apenas as pessoas com a função de segurança de Administrador do Sistema, Personalizador de Sistema ou CEO – Gestor Empresarial podem criar processos que se apliquem a todo o ambiente. As pessoas com outros direitos de acesso podem criar processos com nível de acesso limitado. Por exemplo, as pessoas com o nível de acesso de Utilizador podem criar fluxos de trabalho para utilização pessoal com registos que possuam.  
  
 A seguinte tabela mostra o nível de acesso de processos com base nas funções de segurança predefinidas.  
  
|||  
|-|-|  
|**Funções de segurança**|**Nível de acesso**|  
|CEO – Gestor Empresarial|Organização|  
|Administrador de Sistema|Organização|  
|Personalizador de Sistemas|Organização|  
|Vice-Presidente de Marketing|Nível Principal: Unidades de Negócio Subordinadas|  
|Vice-Presidente de Vendas|Nível Principal: Unidades de Negócio Subordinadas|  
|Gestor de Serviço|Unidade de Negócio|  
|Gestor de Marketing|Unidade de Negócio|  
|Gestor de Vendas|Unidade de Negócio|  
|Gestor da Agenda|Unidade de Negócio|  
|Representante de Suporte ao Cliente|Utilizador|  
|Profissional de Marketing|Utilizador|  
|Vendedor|Utilizador|  
|Agendador|Utilizador|  
  
> [!NOTE]
>  Embora as pessoas possam criar fluxos de processo de negócio, fluxos de trabalho em tempo real ou processos de ação, precisam de ter os privilégios **Ativar Fluxos de Processo de Negócio** ou **Ativar Processos em Tempo Real** para os ativar.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Saiba mais sobre os fluxos de trabalho e Ações  
 Os processos podem verificar condições, aplicar lógica de ramificação e executar ações. Efetuam estas ações numa série de passos. A seguinte tabela descreve os passos disponíveis em processos de fluxo de trabalho e ação. Para obter mais detalhes, veja os tópicos de cada tipo de processo.  
  
|Passo|Tipo de processamento|Descrição|  
|----------|------------------|-----------------|  
|**Fase**|Fluxo de Trabalho, Ação|As fases facilitam a leitura da lógica de fluxo de trabalho e explicam a lógica de fluxo de trabalho. No entanto, as fases não afetam a lógica ou o comportamento de fluxos de trabalho. Se um processo tiver fases, todos os passos no processo têm de estar incluídos numa fase.|  
|**Condição de Verificação**|Fluxo de Trabalho, Ação|Uma declaração lógica "if-\<condição> then".<br /><br /> Pode verificar os valores do registo em que o fluxo de trabalho está a ser executado, qualquer um dos registos ligados a esse registo numa relação N:1 ou qualquer um dos registos criados por passos anteriores. Com base nesses valores, pode definir passos adicionais quando a condição for `true`.|  
|**Ramo Condicional**|Fluxo de Trabalho, Ação|Numa declaração lógica "else-if-then", o editor utiliza o texto "Otherwise, if \<condição> then:"<br /><br /> Selecione uma condição de verificação que definiu anteriormente e pode adicionar um ramo condicional para definir passos adicionais quando a condição de verificação devolver o valor `false`.|  
|**Ação Predefinida**|Fluxo de Trabalho, Ação|Numa declaração lógica "else", o editor utiliza o texto "Otherwise:"<br /><br /> Selecione uma condição de verificação, ramo condicional, condição de espera ou ramo de espera paralelo que definiu anteriormente e pode utilizar uma ação predefinida para definir passos para todos os casos que não correspondam aos critérios definidos nos elementos do ramo ou condição.|  
|**Condição de Espera**|Apenas Fluxo de Trabalho em Segundo Plano|Permite que um fluxo de trabalho em segundo plano se coloque a si mesmo em pausa até que os critérios definidos pela condição sejam cumpridos. O fluxo de trabalho começa de novo automaticamente quando os critérios na condição de espera forem cumpridos.|  
|**Ramo de Espera Paralelo**|Apenas Fluxo de Trabalho em Segundo Plano|Define uma condição de espera alternativa para um fluxo de trabalho em segundo plano com um conjunto correspondente de passos adicionais que são efetuados apenas quando os critérios iniciais são cumpridos. Pode utilizar ramos de espera paralelos para criar limites de tempo na sua lógica de fluxo de trabalho. Estes ajudam a impedir que o fluxo de trabalho aguarde indefinidamente até que os critérios definidos numa condição de espera sejam cumpridos.|  
|**Atribuir Valor**|Ação|Define um valor para uma variável ou parâmetro de saída no processo.|  
|**Criar Registo**|Fluxo de Trabalho, Ação|Cria um novo registo para uma entidade e atribui valores aos atributos.|  
|**Atualizar Registo**|Fluxo de Trabalho, Ação|Pode atualizar o registo em que o fluxo de trabalho está a ser executado, qualquer um dos registos ligados a esse registo numa relação N:1 ou qualquer um dos registos criados por passos anteriores.|  
|**Atribuir Registo**|Fluxo de Trabalho, Ação|Pode atribuir o registo em que o fluxo de trabalho está a ser executado, qualquer um dos registos ligados a esse registo numa relação N:1 ou qualquer um dos registos criados por passos anteriores.|  
|**Enviar E-mail**|Fluxo de Trabalho, Ação|Envia um e-mail. Pode optar por criar uma nova mensagem de e-mail ou utilizar um modelo de e-mail configurado para a entidade do registo no qual o fluxo de trabalho está a ser executado ou em qualquer uma das entidades que tenha uma relação N:1 com a entidade ou a entidade dos registos criados por passos anteriores.|  
|**Iniciar Fluxo de Trabalho Subordinado**|Fluxo de Trabalho, Ação|Inicia um processo de fluxo de trabalho que foi configurado como um fluxo de trabalho subordinado.|  
|**Alterar Estado**|Fluxo de Trabalho, Ação|Altera o estado do registo em que o processo está a ser executado, qualquer um dos registos ligados a esse registo numa relação N:1 ou qualquer um dos registos criados por passos anteriores.|  
|**Parar Fluxo de Trabalho**|Fluxo de Trabalho, Ação|Interrompe o fluxo de trabalho ou ação atual. Pode definir um estado **Com Êxito** ou **Cancelado** e especificar uma mensagem de estado.|  
|**Passo Personalizado**|Fluxo de Trabalho, Ação|Por predefinição, fornece extensões para os elementos lógicos disponíveis. Os passos podem incluir condições, ações, outros passos ou uma combinação destes elementos. Os programadores podem criar passos de fluxo de trabalho personalizados. Por predefinição, não existem passos personalizados disponíveis.|

  

