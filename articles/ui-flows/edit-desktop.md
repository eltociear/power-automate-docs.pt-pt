---
title: Saiba como editar fluxos de IU para computador | Microsoft Docs
description: Saiba como editar fluxos de IU para computador.
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
ms.date: 03/24/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a6b34a58dc028d6d0df9bf03f66a04666998ac69
ms.sourcegitcommit: aefd1ebedfbd8c6cc3d08397ac171cb4ba5b5315
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/30/2020
ms.locfileid: "3412988"
---
# <a name="edit-desktop-ui-flows"></a>Editar fluxos de IU para computador

Os fluxos de IU para computador automatizam as aplicações para computadores Windows. Veja os [Problemas conhecidos](create-desktop.md#known-issues-and-solutions) para saber mais acerca dos problemas que poderá encontrar, das soluções para esses problemas e dos cenários que não são suportados nesta versão.

## <a name="prerequisites"></a>Pré-requisitos
Um fluxo de IU para computador. [Crie um fluxo de IU para computador agora](create-desktop.md#create-and-test-desktop-ui-flows) se não tiver um para editar.

## <a name="edit-actions"></a>Editar ações

![Editar ações](../media/edit-desktop/edit-actions.png "Editar ações")

Pode editar a gravação para:

-   Modificar o valor das ações que a suportem.
-   Eliminar um passo.
-   Eliminar a gravação.
-   Alterar a ordem das ações ao arrastar e largar. Tenha cuidado ao fazê-lo, uma vez que poderá interromper a consistência da gravação.

Os parâmetros avançados permitem-lhe alterar:

-  O atraso depois de a ação ter sido executada. Por exemplo, pode adicionar um atraso de um segundo ao alterar PT0S para PT1S. Este atraso poderá ser útil quando a aplicação de destino tem um tempo de resposta lento, que não é concluído antes do próximo passo do fluxo de IU.
-   O [seletor](edit-desktop.md#set-the-selector) do elemento da interface de utilizador de destino.


## <a name="add-a-recording"></a>Adicionar uma gravação

Pode querer gravar o fluxo de IU em várias sessões. Depois de ter concluído a primeira gravação, pode proceder da seguinte forma:

1. Iniciar sessão no [Power Automate](https://flow.microsoft.com).
1. Selecione **Os meus fluxos** > **Fluxos de IU**.
1. Selecione o fluxo de IU que quer editar.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Selecione **Editar**. 
1. Selecione **Novo passo**.

   ![Novo passo](../media/edit-desktop/new-step.png "Novo passo")

1. Selecione **Gravar aplicação** na lista de ações.

   ![Gravar aplicação](../media/edit-desktop/select-record-ui-actions.png "Gravar aplicação")

1. Selecione **Iniciar gravador**.

   ![Selecione Iniciar gravador](../media/create-windows-ui-flow/select-launch-recorder.png "Selecione Iniciar gravador")

   O controlo do gravador é apresentado na parte superior do ecrã.

   ![Controlo do gravador](../media/create-windows-ui-flow/recorder-control.png "Controlo do gravador")

1. Inicie a aplicação que quer gravar.

     >[!TIP]
     >À medida que o rato passa sobre os controlos na aplicação, verá que um contorno azul realça cada controlo. Aguarde sempre pelo realce azul antes de selecionar um controlo.
     >
     >Se o realce azul não for apresentado em torno de um elemento, o mesmo poderá não ser gravado adequadamente.

1. Selecione **Gravar** no controlo do gravador.

1. Execute os passos na interface de utilizador da aplicação que está a gravar e, em seguida, selecione **Concluído** no controlo do gravador.
1. Selecione **Guardar** e, em seguida, teste o fluxo de IU.

## <a name="add-a-manual-action"></a>Adicionar uma ação manual

Depois de ter gravado uma aplicação com, pelo menos, uma ação, poderá adicionar manualmente qualquer uma das seguintes ações para essa aplicação.

| **Ação**          | **Comentário**                                                       |
|---------------------|-------------------------------------------------------------------|
| Fechar aplicação   |                                                                   |
| Clicar com o botão direito do rato         |                                                                   |
| Enviar teclas           | Envie teclas e combinações de teclas, como CTRL + C.                             |
| Clicar com o botão esquerdo do rato          |                                                                   |
| Obter texto            | Leia o texto de um elemento da interface de utilizador e, em seguida, utilize-o como uma saída. |
| Introduzir texto          |                                                                   |
| Obter elemento ativado | Verifique se um elemento da interface de utilizador está ativado ou desativado.         |
| Limpar elemento       | Limpe o valor num elemento da interface de utilizador editável.             |
| Aguardar alguns segundos    | Aguarde antes de continuar para o próximo passo.                           |

Siga estes passos para adicionar uma ação manual:

1. Iniciar sessão no [Power Automate](https://flow.microsoft.com).
1. Selecione **Os meus fluxos** > **Fluxos de IU**.
1. Selecione o fluxo de IU que quer editar.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Selecione **Editar**. 
1. Selecione o cartão de gravação que contém os passos ao qual quer adicionar um novo passo.
   O cartão é expandido e são apresentados os passos gravados.

   ![Selecionar o cartão de gravação](../media/edit-desktop/manual-select-recording-card.png)

1. Selecione **Adicionar uma ação** no cartão de gravação, imediatamente abaixo do último passo gravado.
   Verá a lista de ações manuais listadas anteriormente nas instruções. 

1. Selecione a ação que quer adicionar. Neste caso, selecionei **Obter elemento ativado**, mas pode selecionar qualquer ação que faça sentido para o seu cenário.

   ![Selecionar ação para adicionar.png](../media/edit-desktop/select-action-to-add.png)

Depois de a ação ter sido adicionada, terá de definir o **Seletor** nas opções avançadas da ação.

![Opções avançadas da ação](../media/edit-desktop/action-advanced-options.png "Opções avançadas da ação")

### <a name="set-the-selector"></a>Definir o seletor

O seletor identifica o elemento da interface de utilizador no qual a ação é executada durante a reprodução. Recomendamos que copie/cole estas informações a partir de um passo separado que vise o mesmo elemento da interface de utilizador, se possível.

O formato do seletor é:

```json
{  
   "type":"WinUIA",
   "parameters":{  
      "elementStack":[  

      ],
      "elementXPath":""
   }
}
```

Terá de fornecer os dados para os campos **elementStack** e **elementXPath** do elemento do seletor.

Veja a seguir um exemplo do possível aspeto do **elementStack**.

![Pilha de elementos](../media/edit-desktop/elementstack.png "Pilha de elementos")

Pode capturar o **elementXPath** com o [Gravador de IU WinAppDriver](https://blogs.windows.com/windowsdeveloper/2018/06/20/introducing-winappdriver-ui-recorder/).

![Ferramenta WAD](../media/edit-desktop/wad-tool.png "Ferramenta WAD")

Remova o primeiro elemento (tudo antes de /Window) antes de utilizar o resultado no **elementXPath** do seletor.

Teste o fluxo de IU para confirmar se o seletor funciona corretamente.

## <a name="use-advanced-controls"></a>Utilizar controlos avançados

Pode incorporar controlos avançados como **condições**, **alternar casos** e ações para **terminar** nos seus fluxos de IU.

Pode realizar estas operações avançadas ao realizar os seguintes passos num fluxo de IU existente.

1. Selecione o fluxo de IU que criou > **Mais comandos** (...) > **Editar**.

1. Selecione **+** > **Adicionar uma ação** na seta para baixo do passo do fluxo de IU ao qual pretende adicionar uma lógica.

   ![Adicionar uma ação](../media/edit-desktop/add-action.png)

1. Selecione **Incorporado** e, em seguida, selecione uma das ações de controlo disponíveis.

   ![Incorporada](../media/edit-desktop/select-built-in.png)

1. Complete a expressão que precisa de ser avaliada. Pode utilizar conteúdo dinâmico e expressões para avaliar a condição e alternar os controlos. Adicionalmente, pode utilizar qualquer saída que seja criada pelos passos anteriores do fluxo de IU.

   ![Cartão de condição](../media/edit-desktop/condition-card.png)


## <a name="add-a-recording-of-a-remote-computer-using-image-recognition-preview"></a>Adicione uma gravação de um computador remoto usando o reconhecimento de imagens (Pré-visualização)

[!INCLUDE[cc-beta-prerelease-disclaimer](../includes/cc-preview-features-expect-changes.md)]

O reconhecimento de imagens nos fluxos de IU é uma funcionalidade de pré-visualização e está atualmente disponível ao gravar um computador remoto através da aplicação Ligação ao Ambiente de Trabalho Remoto (RDC).
 

### <a name="what-is-image-recognition"></a>O que é o reconhecimento de imagens?

Atualmente, os fluxos de IU no ambiente de trabalho são registados principalmente utilizando APIs de acessibilidade (UI Automation e WinAppDriver) para detetar os controlos na árvore de IU do Microsoft Windows. Por vezes, a árvore de IU não está disponível, como aplicações baseadas na Web ou em Java. A árvore de IU pode não ser fiável, como quando os IDs de um controlo mudam frequentemente ou entre sessões. 

Com o reconhecimento de imagem, as localizações de cliques e outros detalhes são visualmente combinados durante a reprodução, expandindo grandemente o leque de aplicações que podem ser automatizadas. 

### <a name="use-image-recognition-to-record-a-remote-computer"></a>Use o reconhecimento de imagem para gravar um computador remoto

 
1. Num fluxo de IUI novo ou existente, vá ao separador Entradas e crie duas novas entradas de **texto sensível**, uma para o nome de utilizador e outra para a palavra-passe que serão usados para iniciar sessão no dispositivo remoto. As entradas de texto sensível permitem-lhe passar os valores dinamicamente ao testar ou chamar o fluxo de IU de outro fluxo, sem que sejam armazenados ou registados pelo próprio fluxo de IU.

   ![Texto sensível ](../media/create-remote-desktop/ir-sensitive-text.png)

1. Siga os passos em **Adicionar uma gravação** para iniciar o controlo do gravador para um fluxo de IU novo ou existente.

1. Utilize a aplicação de Ambiente de Trabalho Remoto para ligar ao computador remoto.

1. Expanda a janela do Ambiente de Trabalho Remoto para o ecrã completo.

1. Selecione **Gravar** no controlo do gravador e selecione **Entendido** no alerta que aparece.

   ![Pop-up](../media/create-remote-desktop/popup.png)

1. Execute os passos no computador remoto e, em seguida, selecione **Concluído** no controlo do gravador.

1. Localize a ação **Iniciar Ambiente de Trabalho Remoto** dentro da sua gravação e, em seguida, introduza as entradas de texto sensível para o nome de utilizador e palavra-passe.

![Texto sensível de nome de utilizador e palavra-passe](../media/create-remote-desktop/ir-launch-emote_desktop-session.png)

1. Selecione **Guardar** e, em seguida, teste o fluxo de IU.

>[!IMPORTANT]
>Quando chama este fluxo de IU de um fluxo automatizado, recomenda-se utilizar uma solução de gestão de chaves, como o [Azure Key Vault](https://azure.microsoft.com/services/key-vault/) para obter o nome de utilizador e a palavra-passe e, em seguida, passá-los para as entradas de **texto sensível** no fluxo de IU dinamicamente, em vez de as armazenar no próprio fluxo. 

>[!TIP]
> Ativar **Entradas seguras** no menu **Definições** para a ação **Executar um fluxo de IU para ambiente de trabalho** no fluxo que chama o fluxo de IU. Isto garante que as entradas não são armazenadas no histórico de execuções.

### <a name="use-the-extract-text-from-image-action-while-recording-to-retrieve-an-output-from-a-remote-computer"></a>Utilize o Texto de Extração da ação Imagem enquanto grava para obter uma saída de um computador remoto.

1. Enquanto grava os seus passos, navegue até à localização do texto que deseja capturar.

1. Selecione **Saídas** > **Extrair Texto da Imagem** do controlo do gravador.

1. Siga as solicitações para selecionar uma **área de ancoragem** (uma secção do ecrã que não deverá ser alterada, como a etiqueta junto de um campo).

    ![Área de ancoragem](../media/create-remote-desktop/ir-anchors.png)

1.  Selecione a **área de destino** (a área a partir da qual o texto será extraído com OCR).

    ![Área de destino](../media/create-remote-desktop/ir-targets.png)

1.  Introduza um nome para a saída.

1.  Selecione **Concluído** no controlo do gravador.

1.  Selecione **Guardar** e, em seguida, teste o fluxo de IU.


### <a name="known-issues-for-remote-desktop-recordings"></a>Problemas conhecidos para gravações de Ambiente de Trabalho Remoto

1. Certifique-se de que todas as entradas necessárias (nome de computador, nome de utilizador e palavra-passe) são preenchidas e guardadas antes de gravar novos passos no mesmo fluxo de IU.

1. Para se ligar a uma sessão de ambiente de trabalho remoto existente, a sessão deve ter sido iniciada anteriormente no mesmo fluxo de IU.

1. A forma recomendada de iniciar a Ligação ao Ambiente de Trabalho Remoto (RDC) ao gravar é a partir da aplicação de Ligação ao Ambiente de Trabalho Remoto (mstc.exe) do menu Iniciar. Se as ações de Segurança do Windows forem gravadas para além da ação **Iniciar Ambiente de Trabalho Remoto**, estas devem ser removidas do estruturador para que a reprodução não seja interrompida (isto pode acontecer quando a sessão de Ambiente de Trabalho Remoto é iniciada a partir de um atalho).

1. A reprodução pode falhar se o fluxo de IU for gravado num ecrã com dimensionamento de ecrã (Definições do Windows > Monitor > Dimensionamento de Ecrã) definido para um valor diferente de 100%. Como solução alternativa, certifique-se de que o dimensionamento de ecrã está definido para 100% antes da gravação.


## <a name="handle-error-conditions"></a>Lidar com condições de erro

Podem surgir condições inesperadas durante a reprodução. Estas condições podem fazer com que os fluxos de IU falhem. Pode utilizar funcionalidades avançadas de processamento de erros para criar passos alternativos para quando surgirem condições inesperadas. 

Eis os passos que tem de seguir para o fazer.

1. Inicie sessão no [Power Automate](https://powerautomate.microsoft.com) com a sua conta escolar ou profissional.
1. Selecione **Os meus fluxos** > **Fluxos de IU**.
1. Selecione **Mais comandos** (os três pontos verticais para o fluxo de IU que pretende editar).
1. Selecione **Editar**.
1. Selecione a seta para baixo que se encontra imediatamente antes do passo do fluxo de IU ao qual pretende adicionar processamento de erros e, em seguida, selecione **+** (Inserir novo passo).
   
   Na seguinte imagem, vamos inserir o novo passo antes do passo **PostElementText 1**. Isto significa que, se **PostElementText 1** falhar, serão executados os passos alternativos que definir a seguir.

      ![Imagem a mostrar a introdução de um novo passo](../media/edit-desktop/insert-new-step.png) 

1. Selecione **Adicionar um ramo paralelo**.

    ![Imagem a mostrar a adição de um ramo paralelo e outras opções](../media/edit-desktop/add-parallel-branch.png)

1. Selecione a ação que pretende executar no ramo paralelo caso exista uma falha quando o fluxo de IU for executado.

   Pode selecionar **Gravar aplicação** para criar uma nova gravação para o ramo paralelo ou selecionar **Terminar** nas ações **Incorporadas** para simplesmente sair do fluxo de IU se ocorrer uma falha.

    ![Imagem a mostrar as opções do ramo paralelo](../media/edit-desktop/add-parallel-branch.png)

   >[!NOTE]
   >Por predefinição, a ação que adicionar ao ramo paralelo será executada apenas se o passo anterior falhar. Pode selecionar **...** no ramo paralelo > **Configurar a execução posterior** para alterar o comportamento predefinido. 

      ![Imagem a mostrar as opções, incluindo Configurar a execução posterior](../media/edit-desktop/configure-run-after.png)

1.  A partir deste ecrã, pode selecionar a condição na qual pretende que o ramo paralelo seja executado. Pode selecionar uma das quatro opções disponíveis.

    ![Imagem a mostrar as opções de execução posterior](../media/edit-desktop/run-after-options.png)

    Nota: Não conseguirá guardar um fluxo de IU que tenha o ramo principal e o ramo paralelo definidos para serem executados na mesma condição.



## <a name="enable-coordinate-based-playback"></a>Ativar a reprodução baseada em coordenadas

A reprodução baseada em coordenadas utiliza o desvio de ecrã relativo como suporte que ajuda os fluxos de IU a localizar objetos-alvo que a arquitetura de automatização de IU do Windows predefinida não consegue localizar durante a reprodução. 

Eis algumas das razões pelas quais a arquitetura de automatização da IU do Windows predefinida poderá não localizar objetos-alvo durante a reprodução:

- A aplicação legada que está a automatizar poderá não utilizar tecnologias de programação que suportem a arquitetura de automatização de IU do Windows.
- A aplicação ou os respetivos controlos poderão não ter um XPath, nome ou IDs de automatização de IU exclusivos. 
- A aplicação tem controlos dinâmicos cujos nomes ou IDs poderiam mudar. 
- A aplicação tem controlos que não têm nomes, IDs, identificadores exclusivos, etc.

>[!TIP]
>Utilize o mesmo dimensionamento e resolução, e maximize a aplicação-alvo durante a gravação para melhorar a precisão da reprodução baseada em coordenadas.

Siga estes passos após gravar um script de fluxo de IU:

1. Expanda o passo que inicia ou anexa a aplicação.
   
   Este é normalmente o primeiro passo do script de gravação.
1. Selecione **Mostrar opções avançadas**.
1. Localize as propriedades **Utilizar reprodução de coordenadas**.
1. Selecione **Sim** na lista para permitir a reprodução baseada em coordenadas.

>[!TIP]
> Pode ativar ou desativar a opção **Utilizar reprodução de coordenadas** para cada aplicação para aplicar a definição a todos os passos efetuados na aplicação.  


>[!WARNING]
>Com a reprodução baseada em coordenadas, a automatização poderá selecionar controlos que não fazem parte da aplicação-alvo devido a várias razões, por exemplo, quando as aplicações-alvo da IU mudam drasticamente.


## <a name="next-steps"></a>Passos seguintes

- Saiba como [executar o fluxo de IU](run-ui-flow.md) que acabou de editar.

- Se quiser fazer mais com os fluxos de IU, poderá também experimentar os fluxos de IU com parâmetros de [entrada e saída](inputs-outputs-web.md).

