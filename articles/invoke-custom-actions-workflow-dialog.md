---
title: Invocar ações personalizadas a partir de um fluxo de trabalho ou diálogo | MicrosoftDocs
description: Saiba como invocar uma ação personalizada a partir de um fluxo de trabalho
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
ms.openlocfilehash: a35523209e3db8444da71c0757db29fa21de08b3
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297918"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Invocar ações personalizadas a partir de um fluxo de trabalho


Os fluxos de trabalho têm várias funcionalidades que suportam cenários empresariais. A chamada de ações de operações de dados básicas para um registo, tais como criar, atualizar e eliminar, a partir de um fluxo de trabalho resolve alguns cenários de negócios. Contudo, se agrupar as capacidades dos fluxos de trabalho com o poder das ações personalizadas invocadas diretamente a partir de um fluxo de trabalho, adiciona uma gama totalmente nova de cenários de negócio à sua aplicação sem ter de escrever código.  
  
 Vamos ver o cenário no qual uma ação personalizada é invocada a partir de um fluxo de trabalho. Invocaremos uma ação personalizada para pedir a aprovação do gerente quando um desconto numa determinada oportunidade exceder 20%.  
  
<a name="action"></a>   
## <a name="example-create-a-custom-action-using-the-opportunity-entity"></a>Exemplo: Criar uma ação personalizada através da entidade oportunidade
  
1. No [explorador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), selecione **Processos**.  
  
2.  Na barra de navegação, escolha **Novo**. Dê um nome ao processo e selecione a categoria **Ação**.  
  
 Para pedir uma aprovação para o desconto, estamos a utilizar uma ação personalizada denominada **Processo de Aprovação**. Adicionámos a um parâmetro de entrada, **SpecialNotes**, e um passo **Enviar Correio Eletrónico** para criar uma nova mensagem e enviar um pedido para aprovação do gestor, conforme apresentado aqui.  
  
 ![Adicionar um passo – enviar e-mail](media/enable-custom-action-approval-proces-sadd-email.png "Adicionar um passo – enviar e-mail")  
  
 Para configurar a mensagem de correio eletrónico, escolha **Definir Propriedades**. Quando o formulário é aberto, utilize o **Assistente de Formulários** para adicionar notas especiais e outras informações à mensagem, como realçado na captura de ecrã. Para adicionar notas especiais, coloque o cursor onde pretende que elas sejam apresentadas na mensagem e, em seguida, no **Assistente de Formulários**, em **Pesquisar**, escolha, **Argumentos** na primeira lista pendente, escolha **SpecialNotes** na segunda lista pendente e selecione **OK**.  
  
 ![Configurar o e-mail](media/enable-custom-action-approval-process-setup-email.png "Configurar e-mail")  
  
 Antes de poder invocar a ação a partir do fluxo de trabalho, tem de a ativar. Depois de ter ativado a ação, poderá ver as propriedades desta selecionando **Ver propriedades**.  
  
 ![Ativar a ação personalizada – processo de aprovação](media/enable-custom-action-approval-process-activate-action.png "Ativar a ação personalizada – processo de aprovação")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Invocar uma ação personalizada de um fluxo de trabalho  
  
1. No [explorador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), selecione **Processos**.   
  
2.  Na barra de navegação, escolha **Novo**. Dê um nome ao processo e selecione a categoria **Fluxo de Trabalho**.  
  
 Criámos um fluxo de trabalho que invoca a ação personalizada **Processo de Aprovação** sempre que é necessária aprovação do gestor para um desconto superior a 20% para uma oportunidade.  
  
 ![Definir as propriedades da ação a partir do fluxo de trabalho](media/enable-custom-action-from-workflow.png "Definir as propriedades da ação a partir do fluxo de trabalho")  
  
 Pode definir as propriedades de entrada da ação escolhendo **Definir Propriedades**. Adicionámos um nome da conta relacionada com a oportunidade nas notas especiais. No **Assistente de Formulários**, em **Procurar**, selecione **Conta** na primeira lista pendente, selecione **Nome da Conta** na segunda lista pendente e, em seguida, selecione **OK**. A propriedade **Destino** é necessária e é povoada pelo sistema. A **{Opportunity(Opportunity)}** na propriedade **Target** é a mesma oportunidade em que o fluxo de trabalho da chamada está em execução.on. Em alternativa, pode escolher uma oportunidade específica para a propriedade Destino com recurso à pesquisa.  
  
 ![Definir os parâmetros de entrada da ação ApprovalProcess](media/enable-customaction-workflow-set-properties.png "Definir os parâmetros de entrada da ação ApprovalProcess")  
  



