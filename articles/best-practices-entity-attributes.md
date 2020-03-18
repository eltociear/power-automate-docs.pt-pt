---
title: Melhores práticas para utilizar os atributos de entidade do fluxo do processo de negócio | Microsoft Docs
description: Saiba quais são as melhores práticas para utilizar os atributos de entidade do fluxo do processo de negócio.
ms.custom: ''
ms.date: 04/23/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Business Process Flows
helpviewer_keywords:
- flow
- process flow
- business process flow
- process
- workflow
author: msftman
ms.author: deonhe
manager: kvivek
ms.openlocfilehash: 8a5fb3cc698f20f025089524e6198c158f710980
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193962"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Melhores práticas para utilizar os atributos do fluxo do processo de negócio



Os atributos legados relacionados com processos em entidades foram preteridos. Veja a seguir algumas melhores práticas para utilizar o atributo *Fase Ativa* (activestageid) na entidade do fluxo do processo de negócio. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Relatórios sobre a fase ativa de um fluxo de processo de negócio

Vamos supor que quer obter uma vista do seu pipeline de vendas através da criação de um relatório sobre a fase ativa em que o **Processo de Vendas da Oportunidade Potencial** se encontra.

Anteriormente, para criar um relatório sobre os processos de negócio por fase, podia definir-se uma vista de cada entidade relacionada do fluxo de processo de negócio e, em seguida, criar relatórios no campo *Fase Ativa* (activestageid).

Como o campo *Fase Ativa* (activestageid) foi preterido nas entidades relacionadas, existem duas formas de criar relatórios sobre os fluxos do processo de negócio.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Opção 1: Vistas e gráficos na entidade do fluxo do processo de negócio **(Recomendado)**

Nas versões 9.0 e superiores, cada fluxo do processo de negócio cria a sua própria entidade do Common Data Service, normalmente com o mesmo nome do fluxo do processo de negócio. Para criar relatórios sobre o fluxo do processo de negócio, selecione a entidade do fluxo do processo de negócio para a qual pretende criar um relatório e, em seguida, crie vistas e gráficos, tal como fazia anteriormente.

No nosso exemplo, siga estes passos para aceder à entidade **Processo de Vendas da Oportunidade Potencial**:
1. Aceda a https://make.powerapps.com.
1. Selecione **Dados**.
1. Selecione **Entidades**.
1. Defina o filtro como **Tudo**.
1. Procure e, em seguida, selecione a entidade **Processo de Vendas da Oportunidade Potencial**.

   ![entidade do processo de vendas da oportunidade potencial](media/best-practices-entity-attributes/lead-opportunity-process.png)

Aqui, pode definir as vistas e os gráficos de tal como faz em qualquer outra entidade.

![detalhes da entidade do processo de tradução](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

Uma vantagem desta abordagem é poder utilizar uma única vista ou um único gráfico para criar relatórios em fluxos do processo de negócio que abrangem várias entidades.

Além disso, como a entidade do fluxo do processo de negócio não é diferente de qualquer outra entidade personalizada no Common Data Service, pode adicionar campos personalizados à entidade para controlar quaisquer informações adicionais necessárias.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Opção 2: Copiar a fase ativa para uma entidade relacionada

Em alternativa, para continuar a criar relatórios a partir da entidade relacionada, crie um fluxo para copiar o campo *Fase Ativa* (activestageid) da entidade do fluxo do processo de negócio para um campo personalizado nas entidades relacionadas do Common Data Service.

Seguem-se alguns aspetos a ter em consideração quando utilizar esta abordagem:

1.  É possível ter mais do que um fluxo do processo de negócio em execução numa única entidade. Com esta abordagem, é melhor ter um campo personalizado que armazene a fase ativa para cada fluxo do processo de negócio que é executado na entidade. Esta abordagem garante a integridade do relatório.

1.  Como a criação de relatórios se baseia na entidade relacionada, não é possível criar uma vista única que crie relatórios sobre fluxos do processo de negócios que abrangem várias entidades.

## <a name="using-the-active-stage-to-run-logic"></a>Utilizar a fase ativa para executar a lógica

Seguem-se alguns casos em que pode querer executar a lógica baseada na fase ativa:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>Utilizar a fase ativa para executar a lógica do lado do cliente

À medida que utilizar o processo de negócio, podem surgir várias coisas que pode querer fazer automaticamente. Por exemplo:

-   Alterar o fluxo do processo de negócio com base em informações recentemente disponíveis no formulário ou no fluxo do processo de negócio.

-   Mover a fase ativa para a fase anterior ou seguinte, com base nos valores que os utilizadores introduziram para passos ou campos do formulário.

-   Ocultar ou mostrar campos e separadores com base na fase selecionada.

-   Mostrar mensagens informativas e executar cálculos com base nos fluxos do processo de negócio ativos, na fase ativa ou selecionada ou em eventos como mover a fase ativa.

> [!TIP]
> Para cenários como esses, utilize o conjunto de [APIs de cliente](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) suportado para os fluxos do processo de negócio.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Utilizar a fase ativa para executar a lógica do lado do servidor

Poderá haver casos em que a automatização com base nas necessidades do fluxo do processo de negócio tem de ser feita do lado do servidor. Por exemplo:

-   Enviar um e-mail para um utilizador se a fase **Qualificar** do **Processo de Vendas da Oportunidade** estiver ativa durante mais de 15 dias.

-   Criar automaticamente um conjunto de atividades relevantes para a fase ativa do **Processo de Vendas da Oportunidade** sempre que este sofrer alterações.

-   Concluir automaticamente o **Processo de Vendas da Oportunidade** quando a atividade de chamada telefónica para fecho for concluída.

> [!TIP]
> Utilizar fluxos de trabalho clássicos do Common Data Service ou fluxos que definir na entidade para o fluxo do processo de negócio.
> 

Para criar um fluxo de trabalho clássico do Common Data Service que cria atividades para revisões de solução interna e para acompanhar o cliente na fase **Propor** do **Processo de Vendas da Oportunidade**:

1. Crie-o na entidade **Processo de Vendas da Oportunidade** e defina-o para ser executado sempre que o campo **Fase Ativa** da entidade se alterar. 
1. Defina uma condição para verificar se o campo **Fase Ativa** é igual a **Propor**. 
1. Crie um registo de compromisso e chamada telefónica para fazer a revisão interna da solução e a chamada para o cliente para rever a solução, respetivamente.

   ![acompanhar a fase de fecho](media/best-practices-entity-attributes/close-stage-followup.png)
