---
title: Saiba como automatizar tarefas repetitivas com fluxos de botões que aceitam entradas do utilizador | Microsoft Docs
description: O Power Automate simplifica a automatização de tarefas repetitivas. Os fluxos podem mesmo aceitar entradas do utilizador ao executar uma tarefa repetitiva.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5a2fa063b5379999a5dcbe37a56271fccf435cae
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79192376"
---
# <a name="introducing-button-flows-with-user-input"></a>Introdução aos fluxos de botões com entradas de utilizador

Crie um fluxo de botão para executar tarefas de rotina ao tocar simplesmente num botão. Personalize o seu fluxo ao permitir que o utilizador indique detalhes específicos que serão executados quando o fluxo for executado. Este tópico orienta-o ao longo da criação de um fluxo de botão que recebe introduções do utilizador e, depois, da execução do fluxo de botão, destacando como fornecer as introduções do utilizador.

Pode criar um fluxo de botão no site do Power Automate ou na aplicação móvel do Power Automate. Neste tópico, vai utilizar o Website.

### <a name="prerequisites"></a>Pré-requisitos
* Uma conta no site do Power Automate.

## <a name="open-the-template"></a>Abrir o modelo
1. Inicie sessão no [site do Power Automate](https://flow.microsoft.com), introduza **Visual Studio** na caixa de pesquisa e clique ou toque no ícone de pesquisa para encontrar todos os modelos relacionados com o Visual Studio:
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. Selecione o modelo **Open a Priority 2 Bug in Visual Studio**:
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. Selecione o botão **Utilizar este modelo**:
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    Este modelo utiliza os serviços Visual Studio Team Services (VSTS) e Notificações Push. Terá de iniciar sessão nesses serviços se não tiver uma ligação a um deles. O botão **Iniciar sessão** só aparece se tiver de iniciar sessão num serviço.
4. Depois de iniciar sessão em todos os serviços necessários, selecione o botão **Continuar**:
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. (opcional) Altere o nome do fluxo, escrevendo um nome à sua escolha na caixa na parte superior do portal:
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>Personalizar a introdução do utilizador
1. No cartão do acionador, selecione **Editar**:
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. Selecione o ícone **+** para expandir a página, de modo a poder adicionar campos de introdução personalizada:
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. Introduza o **Título da introdução** e a **Descrição da introdução** de cada campo personalizado que pretende disponibilizar quando alguém executa o seu fluxo.  
   
    Neste exemplo, vai criar dois campos de introdução personalizados (**Bug repro steps** e **Bug severity**) para que quem utilize este fluxo possa introduzir os passos para reproduzir o erro e classificar a gravidade do mesmo:  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>Personalizar o erro
1. Toque na barra de título do cartão **Create a new work item (Criar um novo item de trabalho)** :
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. Faça as seleções adequadas para o seu ambiente do VSTS e selecione **Edit (Editar)** :
   
    Por exemplo, escreva **myinstance** para se ligar a myinstance.visualstudio.com.
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. Selecione **Show advanced options (Mostrar opções avançadas)** para revelar os outros campos deste cartão:
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. Coloque o cursor antes do token **Bug title (Nome do erro)** e, em seguida, introduza "Gravidade:" no campo de texto **Title (Nome)** .
5. Com o cursor ainda no campo de texto do título, selecione o token **Bug severity (Gravidade do erro)** e, em seguida, introduza "--".  
6. No campo de texto **Description (Descrição)** , coloque o cursor imediatamente após o token **Bug description (Descrição do erro)** e, em seguida, prima Enter para começar uma linha nova.
7. Coloque o cursor na linha nova e, em seguida, selecione o token **Bug Repro steps (Passos de reprodução do erro)** :
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>Personalizar as notificações push
1. Toque na barra de título no cartão **Send a push notification (Enviar notificação push)** para expandi-lo.
2. Na lista de tokens de conteúdo dinâmico, selecione **See more (Ver mais)** e adicione o token do **URL** no campo de texto **Link (Ligação)** .
3. No campo de texto **Link label (Etiqueta da ligação)** , adicione o token do **Id**.
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. Toque em **Create flow (Criar fluxo)** no menu para criar o fluxo:  ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>Executar o fluxo
Nestas instruções, vai utilizar a aplicação móvel do Power Automate para executar o fluxo de botão que acabou de criar. Vai indicar todas as introduções do utilizador necessárias para criar um erro com um nome, uma descrição, passos de reprodução e um nível de gravidade.  

1. Na aplicação móvel do Power Automate, toque no separador **Botões** e, em seguida, toque no botão **Criar relatório de erros com passos**.
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. Introduza o nome do erro que estiver está a comunicar e toque em **Next (Seguinte)** . Por exemplo:
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. Introduza a descrição do erro que estiver está a comunicar e toque em **Next (Seguinte)** . Por exemplo:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. Introduza os passos para reproduzir o erro que estiver está a comunicar e toque em **Next (Seguinte)** . Por exemplo:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. Introduza a gravidade do erro que estiver está a comunicar e toque em **Done (Concluído)** :  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    O fluxo está em execução.
6. (opcional) Toque no separador **Activity (Atividade)** para mostrar os resultados.
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. (opcional) Veja os resultados detalhados da execução do fluxo ao tocar no separador **Create a new work item (Criar um novo item de trabalho)** .
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)


## <a name="use-different-input-types"></a>Utilizar diferentes tipos de entrada

Os fluxos de botões também podem aceitar tipos de dados formatados. Veja a seguir a lista de tipos de entrada de dados que os fluxos de botões aceitam: 

- Texto
- Listas pendentes (como botões de opção)
- Endereço de e-mail
- Ficheiro (por exemplo, uma fotografia no telemóvel)
- Caixa de verificação Sim ou Não
- Número
- Data (com um seletor de calendário)

Para utilizar estes tipos de entrada, adicione o acionador **Acionar manualmente um fluxo** e, em seguida, adicione qualquer um desses tipos ao fluxo:

![Opções de entrada](media/button-flow-with-user-input-tokens/input-options.png)

Além disso, pode querer designar algumas entradas como obrigatórias e outras como opcionais. Utilize o menu de ação (... no lado direito) em cada campo de texto. Existe um limite de cinco entradas por botão.

![Selecionar tokens opcionais](media/button-flow-with-user-input-tokens/required-optional.png)

## <a name="next-steps"></a>Próximos passos
* [Partilhar fluxos de botões](share-buttons.md)
* [Saiba mais sobre fluxos de botão](introduction-to-button-flows.md)  
* [Saiba mais sobre fluxos de botão com tokens de acionador](introduction-to-button-trigger-tokens.md)  

