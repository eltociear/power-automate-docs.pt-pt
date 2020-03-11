---
title: Aprenda a criar fluxos de IU para Sites | Microsoft Docs
description: Aprenda a automatizar aplicações Web com fluxos de IU.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/28/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 90951e4244ef7caa75bedc522d1bb032e070dbef
ms.sourcegitcommit: 26cda5060446812f3725ccd4fe435839088f50fa
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78244269"
---
# <a name="create-and-test-your-web-ui-flows"></a>Criar e testar os fluxos de IU da Web

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Siga estes passos para criar um fluxo de IU da Web simples:

## <a name="create-a-web-ui-flow"></a>Criar um fluxo de IU da Web

1. Abra a [versão seguinte do Microsoft Edge](https://www.microsoftedgeinsider.com/) ou Google Chrome e, em seguida, navegue até [Power Automate](https://flow.microsoft.com/).

1. Iniciar sessão com a sua conta escolar ou profissional, caso necessário.

1. Selecione **Os meus fluxos** > **Fluxos de IU (pré-visualização)**  > **Novo**.

   ![Criar o novo fluxo de IU](../media/create-windows-ui-flow/create-new.png "Criar novo fluxo de IU")

1. Selecione **Aplicação Web** > **Seguinte**
    
   ![Selecionar a Aplicação Web](../media/create-web-ui-flow/select-web-app.png "Selecionar aplicação Web")

1. Introduza um nome para o fluxo de IU no campo **Nome do fluxo**

1. Introduza o URL do Site que quer automatizar no campo **URL base** e, em seguida, selecione **Iniciar gravador**.

   ![Dar um nome e um URL](../media/create-web-ui-flow/give-a-name.png "Dar um nome e um URL") 

   O IDE Selenium é iniciado.

   >[!TIP] 
   >Sugestão: pode registar ações em múltiplos sites HTTP ou HTTPS no mesmo separador.  

1. No IDE Selenium, selecione o botão vermelho **REC** no canto superior direito do ecrã para iniciar o gravador.

   O URL que escolheu no passo anterior é aberto.

   ![Selecionar Rec](../media/create-web-ui-flow/select-rec.png "Selecionar Rec")

1.  Execute as ações que deseja gravar no site. 
    
    >[!TIP]
    >Na parte inferior direita, pode ver o estado da gravação.

    ![Estado da gravação](../media/create-web-ui-flow/recording-status.png "Estado da gravação")

1.  Quando terminar a gravação, selecione o botão vermelho **Parar** no canto superior direito do IDE Selenium.

    ![Botão Parar](../media/create-web-ui-flow/stop-button.png "Botão Parar" )

1. Selecione o botão **Executar teste atual** no canto superior esquerdo do ecrã para ver o fluxo IU que acabou de criar a ser executado.

    ![Executar teste atual](../media/create-web-ui-flow/run-test.png "Executar teste atual")

   >[!TIP]
   >Pode definir o tempo de espera entre os passos para reduzir a velocidade da reprodução local para fins de teste. Esta definição é apenas para fins de teste e não tem impacto quando o fluxo de IU é implementado.  
  
1. Selecione o botão **Guardar projeto** no canto superior direito do IDE Selenium. Esta ação fecha e carrega o projeto.

Agora que criou um fluxo de IU da Web, utilize-o nos outros fluxos.

## <a name="limitations-and-known-issues-for-web-ui-flows"></a>Limitações e problemas conhecidos dos fluxos de IU da Web

>[!WARNING]
>**As palavra-passe no IDE Selenium são armazenadas em texto simples.**  


**Os fluxo de IU já não registam ou reproduzem aplicações Windows após instalar uma nova versão.**

Confirme se está a utilizar a [versão mais recente](https://go.microsoft.com/fwlink/?linkid=2102613&clcid=0x409)

**Perfil de utilizador temporário para reprodução**

As gravações do IDE Selenium são feitas com o perfil do utilizador atual, mas a reprodução é feita com o perfil de utilizador temporário, o que significa que estes sites que precisam de autenticação podem não pedir as credenciais durante uma sessão de gravação, mas os passos de autenticação serão necessários durante a reprodução. 

Para resolver este problema, o utilizador deve editar manualmente o script para inserir os comandos necessários para o processo de início de sessão.

**Outras limitações**

-   Gravar aplicações de computador durante uma sessão de gravação Web. Se precisar de automatizar aplicações Web e de computador, poderá criar fluxos de IU em separado para cada tipo e depois combiná-los num fluxo.

-   Não existe suporte para a Multi-Factor Authentication (MFA). Utilize um inquilino que não exija MFA.

-   Estes comandos do Selenium IDE não são suportados: Run, AnswerOnNextPrompt, ChooseCancelOnNextConfirmation, ChooseCancelOnNextPrompt, ChooseOkOnNextConfirmation, Debugger, ClickAt, DoubleClickAt, Echo, MouseOut, MouseUpAt e MouseDownAt.

-   O clique com o botão direito não é suportado. 

-   A entrada de fluxo de IU da Web adicional é gerada quando utiliza os comandos Foreach. Para contornar este problema, introduza qualquer valor nos campos extra. Tal não afeta a reprodução.

-   Se o ficheiro .side tiver vários projetos de teste, apenas o primeiro a ser criado será executado. 

     >[!TIP]
     >Observe que o IDE Selenium organiza os testes por nome, não por data de criação, portanto, o primeiro teste criado pode não ser o primeiro na lista.

-   A reprodução diretamente no IDE Selenium pode não se comportar conforme o esperado. No entanto, a reprodução no runtime através da infraestrutura de fluxo de IU comporta-se corretamente.

## <a name="next-steps"></a>Próximos passos

- Saiba como [executar fluxos de IU](run-ui-flow.md).

- Se quiser fazer mais com os fluxos de IU, pode também experimentar fluxos de IU com parâmetros de [entrada e saída](inputs-outputs-web.md).

 
