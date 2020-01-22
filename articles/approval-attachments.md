---
title: Enviar anexos com pedidos de aprovação | Microsoft Docs
description: Saiba como criar fluxos que enviam anexos com pedidos de aprovação.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1506902cdd6afe90d7e12a910e2e14519cae7554
ms.sourcegitcommit: c6c4150daadbcc38ef1a33a5903df531b8461ace
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75943006"
---
# <a name="create-approval-flows-with-attachments"></a>Criar fluxos de aprovação com anexos

Por vezes, precisa de obter um ficheiro aprovado para fins comerciais. Felizmente, pode utilizar as aprovações do Power Automate para o fazer. Por exemplo, suponhamos que é um contabilista e pretende obter a aprovação para uma fatura, pode criar um fluxo instantâneo que permite enviar o ficheiro para aprovação simplesmente ao tocar num botão e selecionar o ficheiro a enviar.

Neste artigo, vai aprender a criar um fluxo de aprovação que envia um anexo que o aprovador precisa de rever antes de decidir se o pedido deve ser aprovado.

## <a name="create-the-flow"></a>Criar o fluxo

1. Inicie sessão no Power Automate.
1. Selecione **Os meus fluxos** > **Novo** > **Instantâneo a partir do zero**.

    ![Novo fluxo em branco instantâneo](./media/approval-attachments/new-instand-blank.png)

1. Atribua um nome ao seu fluxo > pesquise e, em seguida, selecione **Acionar manualmente um fluxo** e, em seguida, selecione **Criar**.

    ![Atribuir um nome ao seu fluxo e selecionar um acionador](./media/approval-attachments/name-flow-trigger.png)

1. Selecione o acionador **Acionar manualmente um fluxo** > **Adicionar uma entrada** > **Ficheiro**.

     Os passos anteriores configuram o seu fluxo para que, quando o fluxo for executado, solicite um ficheiro do utilizador para acionar o seu fluxo.

1. Selecionar **Novo passo**
1. Pesquise **Aprovações** e, em seguida, selecione **Iniciar e aguardar uma aprovação**.
1. Selecione **Aprovar/rejeitar – Primeiro a responder** na lista **Tipo de aprovação** do cartão **Iniciar e aguardar uma aprovação**.
1. Indique as seguintes informações no cartão **Iniciar e aguardar uma aprovação**:

   - **Título** – É uma breve descrição que informa o aprovador a respeito do pedido.
   - **Atribuído a** – A pessoa a quem o pedido é enviado.
   - **Detalhes** – Este texto aparece no pedido de aprovação.

     ![O cartão do pedido de aprovação](./media/approval-attachments/approval-request-card.png)

1. Selecione **Mostrar opções avançadas** para revelar os campos nos quais indicará informações sobre o ficheiro anexado ao pedido.
1. Indique um nome de ficheiro em **Nome dos Ficheiros - 1**

   >[!TIP]
   >Tem de incluir a extensão de ficheiro que corresponde ao tipo de ficheiro que é carregado.

1. Proporcione o conteúdo para o ficheiro que será enviado ao aprovador na caixa **Conteúdo dos Anexos - 1**. 

   Uma forma fácil de o fazer é utilizar o item **Conteúdo do Ficheiro** da lista de conteúdo dinâmico que é apresentada quando seleciona a caixa **Conteúdo dos Anexos - 1**.

     ![Opções avançadas no cartão do pedido de aprovação](./media/approval-attachments/approval-request-card-advanced-options.png)

1. Selecione **Guardar** para guardar o seu fluxo.

## <a name="test-your-flow"></a>Testar o seu fluxo

Pode testar o seu fluxo ao selecionar **Teste** e, em seguida, ao carregar um ficheiro .xlsx.

1. Selecione **Teste**.
1. Selecione **Vou realizar a ação do acionador**.

     ![Testar o seu fluxo](./media/approval-attachments/test-flow.png)

1. Selecione **Teste** > **Continuar** para iniciar o teste.
1. Selecione **Importar**.

     ![](./media/approval-attachments/import-file.png)
1. Localize o ficheiro, selecione-o e, em seguida, selecione **Abrir** para carregar o ficheiro ou a imagem que vai enviar para aprovação.

1. Selecione **Executar fluxo**.

   Verá que a execução do teste é iniciada.

     ![O teste começa](./media/approval-attachments/test-started.png)

1. Selecione **Página de Execuções de Fluxo** para monitorizar o estado do teste.

## <a name="approve-the-request"></a>Aprovar o pedido

A pessoa a quem envia o pedido de aprovação recebe um e-mail, semelhante a esta imagem, onde pode ver o anexo e, em seguida, **Aprovar** ou **Rejeitar** o pedido:

![Ver o e-mail do pedido](./media/approval-attachments/approval-request-mail.png)

>[!TIP]
>Os aprovadores também podem avaliar pedidos no centro de aprovações.

## <a name="learn-more"></a>Saiba mais

Na maioria dos fluxos de aprovação, deve notificar a pessoa que solicita a aprovação da decisão. Siga o [artigo de aprovações modernas](modern-approvals.md#add-an-email-action-for-approvals) para saber como adicionar uma **condição** a um fluxo de aprovação para executar ações específicas com base no **resultado** do pedido.

