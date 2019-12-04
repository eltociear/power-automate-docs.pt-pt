---
title: Saiba como criar fluxos de IU para computador | Microsoft Docs
description: Saiba como criar fluxos de IU para computador para aplicações do Windows.
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 064ab35f68ad36ba52395be7768b95276c5c648d
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74372613"
---
# <a name="create-and-test-desktop-ui-flows"></a>Criar e testar fluxos de IU para computador

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Veja os [Problemas conhecidos](create-desktop.md#known-issues-and-solutions) mais à frente neste tópico para saber mais acerca dos problemas que poderá encontrar, das soluções para esses problemas e dos cenários que não são suportados nesta versão de pré-visualização.


## <a name="create-a-desktop-ui-flow"></a>Criar um fluxo de IU para computador

Nos passos a seguir, vamos demonstrar como automatizar a aplicação de calculadora para somar dois números e, em seguida, armazenar o resultado para utilização posterior.

> [!TIP]
> Pode automatizar outras aplicações de computador do Windows ao seguir um padrão semelhante.

1. Verifique se o dispositivo [está pronto](setup.md) para criar fluxos de IU. <!--Todo: link to the prereqs section-->

1. Utilize a [versão Chromium do Microsoft Edge](https://www.microsoftedgeinsider.com) ou o Google Chrome para abrir o [Power Automate](https://flow.microsoft.com) e, em seguida, inicie sessão com a mesma conta escolar ou profissional que utiliza no dispositivo.

1. Selecione **Os meus fluxos** > **Fluxos de IU (pré-visualização)**  > **Novo**.

   ![Criar o novo fluxo de IU](../media/create-windows-ui-flow/create-new.png "Criar novo fluxo de IU")

1. Escolha **Aplicação de computador** e selecione **Seguinte**.

   ![Selecionar o computador](../media/create-windows-ui-flow/select-desktop.png "Selecionar o computador") 

1. Introduza um nome para o fluxo de IU no campo **Nome do fluxo** e selecione **Seguinte**.

   ![Selecionar o computador](../media/create-windows-ui-flow/give-a-name.png "Selecionar o computador") 

1. Selecione **Seguinte** na parte inferior para ignorar o ecrã opcional **Configurar entradas**, uma vez que não estamos a utilizar entradas nestas instruções.

1. Selecione o cartão **Gravar aplicação** para a expandir.

   ![Selecionar Gravar aplicação](../media/create-windows-ui-flow/select-record-app.png "Selecionar Gravar aplicação")

1. Selecione **Iniciar gravador**.

   ![Selecionar Iniciar gravador](../media/create-windows-ui-flow/select-launch-recorder.png "Selecionar Iniciar gravador")

   O controlo do gravador é apresentado na parte superior do ecrã.

   ![Controlo do gravador](../media/create-windows-ui-flow/recorder-control.png "Controlo do gravador")

1. Inicie a aplicação de calculadora.

     >[!TIP]
     >À medida que o rato passa sobre os controlos na aplicação, verá que um contorno azul realça cada controlo. Aguarde sempre pelo realce azul antes de selecionar um controlo.
     >
     >Se o realce azul não for apresentado em torno de um elemento, o mesmo poderá não ser gravado adequadamente.

1. Selecione **Gravar** no controlo do gravador.
1. Selecione o primeiro número, selecione **+** , selecione o segundo número e, em seguida, selecione **=** .

    ![Aplicação de calculadora](../media/create-windows-ui-flow/app-to-record.png "Aplicação de calculadora")
    
     > [!TIP] 
     > A fiabilidade da automatização será melhorada ao:
     > - Abrir e maximizar as aplicações que quer gravar *antes* de começar a gravar
     > - Iniciar a gravação com um clique na barra de título da aplicação para a destacar.

1. Selecione **Concluído** no controlo do gravador depois de concluir as ações que quer gravar.

1. Feche a aplicação que gravou.

1. Selecione o cartão que começa por “Executar script <app name>” para ver as capturas de ecrã dos passos gravados.

     >[!TIP]
     >Selecione **...**  > **Eliminar** para remover os passos duplicados.

    ![Mostrar os passos gravados](../media/create-windows-ui-flow/show-recorded-steps.png "Mostrar passos gravados")

1. Selecione **Seguinte**. 

1. Selecione **Seguinte** para ignorar o passo opcional **Configurar saídas**, uma vez que não estamos a utilizar saídas nestas instruções.

1. Teste o fluxo de IU ao selecionar o botão **Testar agora** e, em seguida, veja a execução do fluxo de IU.
    
 >[!IMPORTANT]
 >Para obter melhores resultados, não interaja com o dispositivo durante a reprodução.

1. Selecione **Guardar e sair** para guardar o fluxo de IU.

## <a name="next-steps"></a>Passos seguintes

- Saiba como [acionar o fluxo de IU](run-ui-flow.md) que acabou de criar.

- Se quiser fazer mais com os fluxos de IU, poderá também experimentar os fluxos de IU com parâmetros de [entrada e saída](inputs-outputs-web.md).

## <a name="known-issues-and-solutions"></a>Problemas conhecidos e soluções

- Atualmente, as capturas de ecrã são perdidas depois de guardar. Estamos a trabalhar para corrigir este problema.

- Poderá ser útil adicionar uma [ação **Fechar**](edit-desktop.md#add-a-manual-action) no final do fluxo de IU, porque os fluxos de IU iniciam uma nova instância das aplicações a cada teste ou execução.

- Selecione **...**  > **Eliminar** no cartão de ações gravadas para remover as ações desnecessárias/duplicadas. As ações duplicadas podem ser criadas dependendo do tipo e da velocidade com que está a gravar. 

- Os cliques com o botão direito podem não ser reproduzidos corretamente. Nesse caso, durante a gravação, clique com o botão esquerdo para focar os fluxos de IU no elemento da interface de utilizador de destino e, em seguida, clique com o botão direito.

- Se os fluxos de IU não gravarem nem reproduzirem aplicações do Windows depois de instalar uma nova versão, desinstale a versão anterior e instale uma nova versão.


### <a name="unsupported-application-types"></a>Tipos de aplicações não suportadas

-   Interações no Windows (Explorador de ficheiros, menu de inicialização, barra de tarefas e etc.).

-   Browsers (Chrome, IE, Edge, Edge Chromium, Firefox, Mozilla e etc.).
    Em alternativa, veja [Criar um fluxo de IU para a Web](edit-web.md) para automatizar os sites.

-   Aplicações Java.

-   Aplicações de um clique.

-   Aplicações com uma vista Web, como as aplicações Electron.

-   Microsoft Office 2016 e versões anteriores. 

-   Microsoft Office online.

### <a name="unsupported-configurations"></a>Configurações não suportadas

-   Vários ecrãs.

-   Gravar através de um cliente de máquina virtual (Ambiente de Trabalho Remoto, Citrix e etc.).

-   Várias instâncias de uma aplicação onde os títulos da janela principal são idênticos.

-   Aplicações do Windows com títulos idênticos, por exemplo, Microsoft Outlook com várias janelas de correio **Sem título – Mensagem (HTML)** ativas ao mesmo tempo.

-   Sessões de gravação simultâneas num determinado dispositivo.

-   Sessões de reprodução simultâneas num determinado dispositivo. No caso de execuções de fluxos de IU simultâneas, a primeira tem precedência e as restantes falham até que a primeira seja concluída.

-   Reprodução num dispositivo com um esquema de teclado diferente daquele onde foi gravado.

-   Gravação num dispositivo ou numa sessão do Windows enquanto o browser com o Microsoft Flow está num dispositivo ou numa sessão do Windows diferente.

### <a name="unsupported-action-types-and-behaviors"></a>Tipos de ações e comportamentos não suportados

As seguintes ações não serão gravadas:

-   Duplo clique.

-   Movimentação do rato.

-   Passagem do rato.

-   Clique e arraste.

-   Introdução por toque ou com caneta.

-   Abrir aplicação antes da gravação.

<!-- -   Closed app before playback starts. -->

## <a name="unreliable-behaviors-and-workarounds-for-microsoft-office-desktop"></a>Comportamentos não fiáveis e soluções para o Microsoft Office (ambiente de trabalho)
- Afixe o friso antes de começar a reproduzir para evitar problemas que possam ocorrer caso o friso esteja definido para ser ocultado automaticamente durante a reprodução.
- Não selecione itens através de clique e arraste. Por exemplo, não utilize shift-clique para selecionar células no Microsoft Excel e não selecione texto no Microsoft Word ou no Microsoft PowerPoint ao arrastar o rato.
- Alguns elementos podem não funcionar corretamente nos fluxos de IU (pré-visualização) para aplicações de computador do Microsoft Word e Microsoft PowerPoint. Por exemplo, as opções no menu Ficheiro, como começar do zero, clicar com o botão direito do rato nos controlos, como adicionar um parágrafo no Microsoft Word, ou alterar o esquema dos diapositivos no Microsoft PowerPoint podem não funcionar.
