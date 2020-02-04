---
title: Invocar ações personalizadas de um fluxo de trabalho | Microsoft Docs
description: Saiba como invocar uma ação personalizada de um fluxo de trabalho
ms.custom: ''
ms.date: 11/22/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
author: Mattp123
ms.assetid: 1fd5d39e-3dc8-4d1a-8b4b-ccaa303f4bbb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 15cbfdf61a25287714f0244639ec4a3246bd845c
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74355432"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Invocar ações personalizadas de um fluxo de trabalho
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Os fluxos de trabalho têm várias funcionalidades que suportam cenários empresariais. A chamada de ações de operações de dados básicas para um registo, tais como criar, atualizar e eliminar, a partir de um fluxo de trabalho resolve alguns cenários de negócios. No entanto, se conjugar as funcionalidades dos fluxos de trabalho com as das ações personalizadas invocadas diretamente a partir do fluxo de trabalho, consegue adicionar uma gama totalmente nova de cenários empresariais à sua aplicação sem ser necessário escrever código.  
  
 Vejamos o cenário em que uma ação personalizada é invocada a partir de um fluxo de trabalho. Invocaremos uma ação personalizada para pedir a aprovação do gerente quando um desconto numa determinada oportunidade exceder 20%.  
  
<a name="action"></a>   
## <a name="example-create-a-custom-action-using-the-opportunity-entity"></a>Por exemplo: criar uma ação personalizada através da entidade Oportunidade
  
1. No [explorador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), selecione **Processos**.  
  
2.  Na barra de navegação, selecione **Novo**. Atribua um nome ao processo e selecione a categoria **Ação**.  
  
 Para pedir a aprovação do desconto, vamos utilizar uma ação personalizada denominada **Processo de Aprovação**. Adicionámos um parâmetro de entrada, **NotasEspeciais**, e um passo **Enviar e-mail** para criar uma nova mensagem e enviar um pedido de aprovação do gerente, conforme mostrado aqui.  
  
 ![Adicionar um passo – enviar e-mail](media/enable-custom-action-approval-proces-sadd-email.png "Adicionar um passo – enviar e-mail")  
  
 Para configurar a mensagem de e-mail, selecione **Definir Propriedades**. Quando o formulário for aberto, utilize o **Assistente de Formulários** para adicionar notas especiais e outras informações ao e-mail, conforme destacado na captura de ecrã. Para adicionar as notas especiais, coloque o cursor onde pretende que elas apareçam na mensagem e, em seguida, no **Assistente de Formulários**, em **Procurar**, selecione **Argumentos** na primeira lista pendente e **NotasEspeciais** na segunda lista pendente. Em seguida, selecione **OK**.  
  
 ![Configurar o e-mail](media/enable-custom-action-approval-process-setup-email.png "Configurar o e-mail")  
  
 Antes de poder invocar a ação a partir do fluxo de trabalho, tem de a ativar. Após ativar a ação, pode ver as propriedades da mesma ao selecionar **Ver propriedades**.  
  
 ![Ativar a ação personalizada – processo de aprovação](media/enable-custom-action-approval-process-activate-action.png "Ativar a ação personalizada – processo de aprovação")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Invocar uma ação personalizada de um fluxo de trabalho  
  
1. No [explorador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), selecione **Processos**.   
  
2.  Na barra de navegação, selecione **Novo**. Atribua um nome ao processo e selecione a categoria **Fluxo de Trabalho**.  
  
 Criámos um fluxo de trabalho que invoca a ação personalizada **Processo de Aprovação** sempre que o gerente tiver de aprovar descontos superiores a 20% numa oportunidade.  
  
 ![Definir as propriedades da ação a partir do fluxo de trabalho](media/enable-custom-action-from-workflow.png "Definir as propriedades da ação a partir do fluxo de trabalho")  
  
 Pode definir propriedades de entrada da ação ao selecionar **Definir Propriedades**. Adicionámos um nome da conta relacionada com a oportunidade nas notas especiais. No **Assistente de Formulários**, em **Procurar**, selecione **Conta** na primeira lista pendente, selecione **Nome da Conta** na segunda lista pendente e, em seguida, selecione **OK**. A propriedade **Destino** é obrigatória e tem de ser preenchida pelo sistema. A **{Oportunidade(Oportunidade)}** na propriedade **Destino** é a oportunidade onde fluxo de trabalho chamado está a ser executado. Em alternativa, pode escolher uma oportunidade específica para a propriedade Destino com recurso à pesquisa.  
  
 ![Definir os parâmetros de entrada da ação ApprovalProcess](media/enable-customaction-workflow-set-properties.png "Definir os parâmetros de entrada da ação ApprovalProcess")  
  



