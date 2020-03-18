---
title: Pedidos de Exportação de Titulares de Dados RGPD no Power Automate para Contas Microsoft (MSA) | Microsoft Docs
description: Saiba como utilizar o Power Automate para responder a Pedidos de Exportação de Titulares de Dados RGPD para Contas Microsoft.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: Deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 487f19badd67650c686c9e497cad739ee1560885
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195101"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-power-automate"></a>Responder a Pedidos de Exportação de Titulares de Dados GDPR no Power Automate


Como parte do nosso compromisso para o ajudar no seu percurso de preparação para o Regulamento Geral sobre a Proteção de Dados (GDPR), desenvolvemos documentação de ajuda. A documentação não só descreve o que estamos a fazer para nos prepararmos para o GDPR, mas também partilha exemplos de passos que pode seguir neste momento com a Microsoft para suportar a conformidade com o GDPR quando utilizar o Power Automate.

## <a name="manage-export-requests"></a>Gerir pedidos de exportação

O *direito de portabilidade dos dados* permite que os titulares dos dados solicitem uma cópia dos seus dados pessoais num formato eletrónico (isto é, num “formato estruturado interoperável frequentemente utilizado e legível pelo computador”) que possa ser transmitido a outro responsável pelo tratamento de dados.

Utilize o [dashboard de privacidade da Microsoft](https://account.microsoft.com/privacy/) ou o [Power Automate](https://flow.microsoft.com/) para localizar ou exportar dados pessoais de um utilizador específico.

|Dados pessoais|Localização|
|-----------------|-------------------|
|Atividade de produtos e serviços|Dashboard de privacidade da Microsoft|
|Fluxos|Portal do criador do Power Automate|
|Histórico de execuções|Portal do criador do Power Automate|
|Feed de Atividades|Portal do criador do Power Automate|
|Ligações|Portal do criador do Power Automate|

## <a name="export-product-and-service-activity"></a>Exportar a atividade de produtos e serviços

1. Inicie sessão no [dashboard de privacidade da Microsoft](https://account.microsoft.com/privacy/) com a sua Conta Microsoft (MSA).
1. Selecione **Histórico de atividades**.

    ![Histórico de Atividades](./media/gdpr-dsr-export-msa/activityhistory.png) No histórico de atividades, pode procurar as diferentes aplicações e serviços da Microsoft que utiliza.
1. Para exportar dados da **Atividade de Produtos e Serviços**, selecione **Transferir os dados**e, em seguida, selecione **CRIAR NOVO ARQUIVO**.

    ![Transferir os seus dados](./media/gdpr-dsr-export-msa/downloaddata.png)

1. Selecione **Utilização de aplicações e serviços**e, em seguida, selecione **Criar arquivo**.

    ![Transferir os seus dados](./media/gdpr-dsr-export-msa/create-archive.png)
1. É criado um novo arquivo. Selecione **Transferir** para obter os dados da atividade de produtos e serviços exportados.

    ![Transferir](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Exportar um fluxo

Um utilizador final com acesso a um fluxo pode exportá-lo ao seguir estes passos:

1. Inicie sessão no [Power Automate](https://flow.microsoft.com/).

1. Selecione **Os meus fluxos** e, em seguida, o fluxo a exportar.

1. Selecione **... Mais** e, em seguida, **Exportar**.

    ![Exportar fluxo](./media/gdpr-dsr-export/export-flow.png)

1. Selecione **Pacote (.zip)** .

O fluxo estará agora disponível como um pacote zipado. Para obter mais informações, veja a mensagem de blogue sobre [como exportar e importar um fluxo](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exportar histórico de execuções

O histórico de execuções inclui uma lista de todas as execuções de um fluxo. Estes dados incluem o estado do fluxo, a hora de início, a duração e os dados de entrada/saída dos acionadores e das ações.

Um utilizador final com acesso ao fluxo pode seguir estes passos para exportar esses dados:

1. Inicie sessão no [Power Automate](https://flow.microsoft.com/).
1. Selecione a ligação **Os meus fluxos** e, em seguida, o fluxo cujo histórico de execuções pretende exportar.
1. No painel **HISTÓRICO DE EXECUÇÕES**, selecione **Ver tudo**.

    ![Histórico de execuções](./media/gdpr-dsr-export/run-history.png)

1. Selecione **Transferir CSV**.

    ![Transferir CSV](./media/gdpr-dsr-export/download-csv.png)

O histórico de execuções é transferido como um ficheiro .csv para que possa abri-lo no Microsoft Excel ou num editor de texto e analisar os resultados.

## <a name="export-a-users-activity-feed"></a>Exportar o feed de atividades de um utilizador

No [Power Automate](https://flow.microsoft.com/), o feed de atividades mostra o histórico das atividades, as falhas e as notificações de um utilizador. Qualquer utilizador pode ver o seu feed de atividades se seguir estes passos:

1. Inicie sessão no [Power Automate](https://flow.microsoft.com/), selecione o ícone de campainha próximo do canto superior direito e, em seguida, selecione **Mostrar toda a atividade**.

    ![Mostrar feed de atividades](./media/gdpr-dsr-export/show-activity-feed.png)

1. No ecrã **Atividade**, copie os resultados e cole-os num editor de texto, como o Microsoft Word.

    ![Mostrar feed de atividades](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exportar as ligações de um utilizador

As ligações permitem que os fluxos se liguem a APIs, a aplicações SaaS e a outros sistemas de terceiros. Siga estes passos para ver as ligações:

1. Inicie sessão no [Power Automate](https://flow.microsoft.com/), selecione o ícone de engrenagem próximo do canto superior direito e, em seguida, selecione **Ligações**.

    ![Mostrar Ligações](./media/gdpr-dsr-export/show-connections.png)
1. Copie os resultados e cole-os num editor de texto, como o Microsoft Word.
