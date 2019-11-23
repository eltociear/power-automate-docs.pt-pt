---
title: Adicionar um fluxo de trabalho a pedido a um fluxo de processo de negócio
description: ''
author: MSFTMAN
ms.author: Deonhe
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
ms.service: flow
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: 26c79c20-2987-476e-983a-406e0db13034
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7f6319bd0091c4c857e7df133c36b38a0cd78891
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74356835"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>Adicionar um fluxo de trabalho a pedido a um fluxo de processo de negócio
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Pode acionar fluxos de trabalho a pedido a partir de um fluxo do processo de negócio. Pode, por exemplo, adicionar um fluxo de trabalho a pedido a um fluxo de processo de negócio para que uma atividade, como uma tarefa ou e-mail, seja criada sempre que uma fase é concluída. 

Os fluxos de trabalho são ativados em função do local onde larga o fluxo de trabalho no estruturador de fluxo do processo de negócio.
- Processos de fase a pedido. Quando o fluxo de trabalho é largado numa fase do fluxo do processo de negócio, este é acionado à entrada ou saída da fase. 
- Processos globais a pedido. Quando o fluxo de trabalho é largado na área **Fluxos de Trabalho Globais**, este é acionado aquando da ativação ou do arquivamento do processo (quando o estado muda para aplicado, concluído, reativado ou abandonado). 

Tenha em atenção os seguintes requisitos quando adicionar um fluxo de trabalho a um fluxo do processo de negócio.
- No caso dos fluxos de trabalho adicionados a uma fase: só pode utilizar fluxos de trabalho ativos e a pedido criados para a mesma entidade da fase onde quer adicionar o fluxo de trabalho.  
- No caso dos fluxos de trabalho globais: só pode utilizar fluxos de trabalho ativos e a pedido para a entidade primária do fluxo do processo de negócio.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>Adicionar um fluxo de trabalho a pedido a uma fase do fluxo de processo de negócio

Para adicionar um fluxo de trabalho a pedido a partir do estruturador de fluxo do processo de negócio, tem de arrastar o componente de fluxo de trabalho para uma fase de processo ou para a secção dos fluxos de trabalho globais. 

No site do [PowerApps](https://make.powerapps.com), selecione **Orientado por modelos** (no canto inferior esquerdo do painel de navegação). 

Abra o estruturador de fluxo do processo de negócio. Pode fazê-lo de duas formas.
- Se o fluxo do processo de negócio já tiver sido adicionado a uma aplicação, aceda a **Aplicações**, junto à aplicação que pretende selecionar **...** e, em seguida, selecione **Editar**. No estruturador de aplicações, selecione o fluxo do processo de negócio e, em seguida, selecione ![Open business process flow designer](media/dynamics365-open-designer.PNG) (Abrir estruturador de fluxo do processo de negócio).  
- Caso contrário, abra o [explorador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer), no painel de navegação esquerdo, selecione **Processos** e, em seguida, selecione o fluxo do processo de negócio que pretende. 

Decida se quer que o fluxo de trabalho a pedido seja acionado por um dos seguintes eventos de fluxo de processo de negócio. 
- Processos de fase a pedido. Aciona o fluxo de trabalho à entrada ou saída da fase. 
- Processos globais a pedido. Aciona o fluxo de trabalho aquando da ativação ou do arquivamento do processo (quando o estado muda para aplicado, concluído, reativado ou abandonado). 

No exemplo abaixo, há um fluxo de trabalho a pedido chamado **My on demand workflow** que é adicionado à **Fase 1** do fluxo do processo de negócio. 

1. Expanda a fase 1 para mostrar a secção **Processo Acionado**. 
2. Selecione o separador **Componentes** e arraste o **Fluxo de Trabalho** para a secção **Processo Acionado**.
    ![Adicionar um fluxo de trabalho a uma fase](media/add-workflow-to-bpf-1.png) Em alternativa, pode arrastar o **Fluxo de Trabalho** para a secção **Fluxos de Trabalho Globais**, o que aciona o fluxo de trabalho aquando da ativação ou do arquivamento do processo.
 ![Adicionar um fluxo de trabalho à ativação ou arquivamento do processo](media/add-workflow-to-bpf-global.png)
3. Na caixa de pesquisa do separador **Propriedades**, introduza e procure o nome do fluxo de trabalho a pedido que pretende adicionar à fase do fluxo do processo de negócio e, em seguida, selecione **Aplicar**.
    ![Introduzir o nome e selecionar Aplicar](media/add-workflow-to-bpf-2.png)
4. No separador **Propriedades**, em **Acionador**, selecione **Entrada de Fase** ou **Saída de Fase**.  
    ![Selecionar o acionador de fluxo de trabalho](media/workflow-trigger.png)
   
    Em alternativa, quando largar o fluxo de trabalho na secção **Fluxos de Trabalho Globais**, as opções do acionador são **Processo aplicado**, **Processo reativado**,  **Processo abandonado** e **Processo concluído**.

5. Selecione **Atualizar** na barra de ferramentas do estruturador de fluxo do processo de negócio.
 
## <a name="next-steps"></a>Passos seguintes
[Use Workflow processes to automate processes that don't require user interaction](workflow-processes.md) (Utilizar processos de Fluxo de Trabalho para automatizar processos que não necessitam de interação do utilizador) <br/>
[Tutorial: criar um fluxo de processo de negócio para normalizar processos](create-business-process-flow.md) <br/>
[Business process flow automation in Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/) (Automatização de fluxos do processo de negócio no Dynamics 365)
