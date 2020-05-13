---
title: Introdução | Microsoft Docs
description: Comece a automatizar rapidamente o seu trabalho e a sua vida com o Power Automate.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/05/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: bd7d85dc2ec30147202c2838f00c7de6c7c587ad
ms.sourcegitcommit: 4b9261984a554dfccb0d0d77f3d5fdca60e26433
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82852663"
---
# <a name="get-started-with-power-automate"></a>Introdução ao Power Automate 

Bem-vindo! O Power Automate é um serviço que o ajuda a criar fluxos de trabalho automatizados entre as suas aplicações e serviços favoritos para sincronizar ficheiros, obter notificações, recolher dados e mais.

<br/>

> [!VIDEO https://www.youtube.com/embed/hCuxuUaGC6Y]


## <a name="types-of-flows"></a>Tipos de fluxos

O Power Automate é um dos pilares do Power Platform. Fornece uma plataforma de código simples para automatização dos processos e dos fluxos de trabalho. Veja a seguir uma lista dos diferentes tipos de fluxos:

| **Tipo de fluxo**                                                                       | **Caso de utilização**                                                                                  | **Finalidade**                                                                             |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| [Fluxos automatizados](get-started-logic-flow.md)                 | Crie um fluxo que realize uma ou mais tarefas automaticamente depois de ser acionado por um evento. | [Conectores](https://docs.microsoft.com/connectors/) para serviços cloud ou no local. |
| [Fluxos de botão](introduction-to-button-flows.md)              | Execute tarefas repetitivas a partir de qualquer lugar, a qualquer momento, através do dispositivo móvel.                        |                                                                                        |
| [Fluxos agendados](run-scheduled-tasks.md)                    | Crie um fluxo que executa uma ou mais tarefas através de agendamento.             |                                                                                        |
| [Fluxos de processo de negócio](business-process-flows-overview.md) | Defina um conjunto de passos que as pessoas deverão seguir para alcançarem um resultado pretendido.                 | Processos humanos                                                                        |
| [Fluxos de IU](ui-flows/overview.md)                                                | Grave e automatize a reprodução dos passos manuais no software herdado.                    | Aplicações Web e de computador que não têm APIs disponíveis para automatização.    |

Pode criar e gerir todos os fluxos no separador **Os meus fluxos** do Power Automate.

Se for utilizador do Dynamics 365, também poderá estar familiarizado com os processos clássicos do Common Data Service que incluem [fluxos de trabalho](configure-workflow-steps.md), [ações](create-actions.md), [fluxos de tarefas móveis](create-mobile-task-flow.md) e [caixas de diálogo](use-cds-for-apps-dialogs.md).

O primeiro passo é [inscrever-se](sign-up-sign-in.md) ou, se já tiver uma conta do Power Automate, [iniciar sessão](https://flow.microsoft.com/signin) no tablet, computador de secretária ou, mesmo, no telemóvel.

## <a name="check-out-the-start-page"></a>Aceder à página inicial ##

[Na página inicial](https://flow.microsoft.com) do Power Automate, pode [explorar um conjunto diversificado de modelos](https://flow.microsoft.com/templates) e saber mais sobre as funcionalidades essenciais do Power Automate. Pode ficar com uma noção rápida do que é possível fazer e de como o Power Automate pode ajudar a sua empresa e a sua vida.

Com o Power Automate pode:

- Pesquisar facilmente modelos e serviços.

    ![Página inicial do fluxo 1](./media/getting-started/flowhome1.png)

- Escolha entre os serviços mais populares.

    ![Página inicial do fluxo 2](./media/getting-started/flowhome2.png)

- Veja uma descrição geral de cada fluxo.

    ![Página inicial do fluxo 3](./media/getting-started/flowhome3.png)

Cada modelo foi concebido para um fim específico. Por exemplo, existem modelos para lhe enviar uma mensagem SMS quando o seu chefe lhe enviar um e-mail, para adicionar leads do Twitter ao Dynamics 365 ou para fazer uma cópia de segurança dos seus ficheiros. Estes modelos são apenas a ponta do icebergue. Destinam-se a inspirá-lo a criar fluxos personalizados para os processos exatos de que precisa.

## <a name="create-your-first-flow"></a>Criar o primeiro fluxo ##

1. Selecione um modelo que seja útil para si. Um modelo simples é [**Receber lembretes diários no E-mail**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/) :

    ![modelo de lembrete diário](./media/getting-started/template-details.png)

1. Selecione **Continuar**.

    ![Criar ligação](./media/getting-started/create-connection.png)

1. Introduza os endereços de e-mail para os quais o lembrete diário será enviado. Em seguida, introduza a mensagem do lembrete. Por último, selecione **Criar fluxo** e certifique-se de que o fluxo está a ser executado conforme esperado.

    ![Indicar credenciais para a ligação](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > Pode explorar as condições que acionam o fluxo e a ação que resulta desse evento. Experimente as definições para personalizar o fluxo. Pode até adicionar ou eliminar ações.

1. Selecione **Concluído**.

[Siga este tutorial](get-started-logic-template.md) para saber mais sobre a criação de fluxos a partir de modelos.

## <a name="get-creative"></a>Ser criativo ##

Agora que criou o primeiro fluxo a partir de um modelo, utilize qualquer uma das mais de [150 origens de dados](https://flow.microsoft.com/connectors/) que o Power Automate suporta para [criar os seus próprios fluxos do zero](get-started-logic-flow.md).

![Compilação de um fluxo](./media/getting-started/build-a-flow.png)

Quando criar um fluxo a partir do zero, controla todo o fluxo de trabalho. Aqui estão algumas ideias para começar:

- [Fluxos com muitos passos](multi-step-logic-flow.md).
- [Executar tarefas com base numa agenda](run-scheduled-tasks.md).
- [Criar um fluxo de aprovação](wait-for-approvals.md).
- [Observar um fluxo em ação](see-a-flow-run.md).
- [Publicar um modelo](publish-a-template.md).
- [Criar fluxos a partir de um modelo do Microsoft Teams](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/).


## <a name="peek-at-the-code"></a>Pré-visualização do código

Não precisa de ser um programador para criar fluxos, embora o Power Automate disponibilize uma funcionalidade de **Código de pré-visualização** que permite que qualquer pessoa possa analisar o código que é gerado para todas as ações e acionadores num fluxo. Pré-visualizar o código pode proporcionar uma melhor compreensão dos dados que estão a ser utilizados por acionadores e ações. Siga estes passos para pré-visualizar o código que é gerado para os fluxos no estruturador do Power Automate: 

1. Selecione o item de menu **...** no canto superior direito de qualquer **ação** ou **acionador**. 
1. Selecione **Código de pré-visualização**.

    ![Código de pré-visualização](media/getting-started/peek-code.png)

1. Repare na representação JSON completa das ações e dos acionadores. Essa representação inclui todas as entradas, como o texto que introduzir diretamente e as expressões utilizadas. Pode selecionar expressões aqui e, em seguida, colá-las no editor de expressões de **Conteúdo Dinâmico**. Este procedimento pode funcionar como uma forma de verificar se os dados esperados estão presentes no fluxo.

    ![Código de pré-visualização](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Localizar facilmente os fluxos

Quando as suas capacidades criativas começarem a *fluir*, poderá criar muitos fluxos. Não se preocupe, localizar os fluxos é muito fácil – basta utilizar a caixa de pesquisa nos ecrãs **Os meus fluxos**, **Fluxos de equipa**, **Ligações** ou **Soluções** para apresentar apenas os fluxos que correspondem aos termos de pesquisa que introduzir.

![Filtrar ou pesquisar fluxos](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> O filtro de pesquisa localiza apenas os fluxos que tenham sido carregados na página. Se não encontrar o fluxo, experimente selecionar **Carregar mais** na parte inferior da página.

## <a name="get-notifications-when-somethings-wrong"></a>Receber notificações quando ocorrer um problema

Utilize o Centro de notificações do Power Automate (localizado na parte superior direita do estruturador) para ver rapidamente uma lista dos fluxos que falharam recentemente. O centro de notificações apresenta um número que indica o número de fluxos que falharam recentemente.

No centro de notificações, pode navegar para a página **Atividade** do Power Automate para ver todos os fluxos que recentemente foram executados, enviaram notificações ou falharam.

![Centro de notificações](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Utilizar a aplicação móvel ##

Transfira a aplicação móvel do Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows). Com esta aplicação, pode [monitorizar a atividade do fluxo](mobile-monitor-activity.md), [gerir os seus fluxos](mobile-manage-flows.md) e [criar fluxos a partir de modelos](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Estamos aqui ajudar ##

Estamos ansiosos por ver o que pode fazer com o Power Automate e queremos garantir que tem uma excelente experiência. Veja os nossos tutoriais de [aprendizagem guiada](https://flow.microsoft.com/guided-learning/) e [adira à nossa comunidade](https://go.microsoft.com/fwlink/?LinkID=787467) para colocar questões e partilhar as suas ideias. [Contacte o suporte](https://go.microsoft.com/fwlink/?LinkID=787479) caso se depare com quaisquer problemas.
