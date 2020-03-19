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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 49586e7035c4a1796ff624667b2562d2a64c576a
ms.sourcegitcommit: ace3dbcbda208991201b770b9c707ec39faaa0d9
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79384594"
---
# <a name="edit-desktop-ui-flows"></a>Editar fluxos de IU para computador

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Os fluxos de IU para computador automatizam as aplicações para computadores Windows. Veja os [Problemas conhecidos](create-desktop.md#known-issues-and-solutions) para saber mais acerca dos problemas que poderá encontrar, das soluções para esses problemas e dos cenários que não são suportados nesta versão de pré-visualização.

## <a name="prerequisites"></a>Pré-requisitos
Um fluxo de IU para computador. [Crie um fluxo de IU para computador agora](create-desktop.md#create-and-test-desktop-ui-flows) se não tiver um para editar.

## <a name="edit-actions"></a>Editar ações

![Editar ações](../media/edit-desktop/edit-actions.png "Editar ações")

Pode editar a gravação para:

-   Modificar o valor das ações que a suportem.
-   Eliminar um passo.
-   Eliminar a gravação completa.
-   Alterar a ordem das ações ao arrastar e largar. Tenha cuidado ao fazê-lo, uma vez que poderá interromper a consistência da gravação.

Os parâmetros avançados permitem-lhe alterar:

-  O atraso depois de a ação ter sido executada. Por exemplo, pode adicionar um atraso de um segundo ao alterar PT0S para PT1S. Este atraso poderá ser útil quando a aplicação de destino tem um tempo de resposta lento, que não é concluído antes do próximo passo do fluxo de IU.
-   O [seletor](edit-desktop.md#set-the-selector) do elemento da interface de utilizador de destino.


## <a name="add-a-recording"></a>Adicionar uma gravação

Pode querer gravar o fluxo de IU em várias sessões. Depois de ter concluído a primeira gravação, pode proceder da seguinte forma:

1. Inicie sessão no [Power Automate](https://flow.microsoft.com).
1. Selecione **Os meus fluxos** > **Fluxos de IU (pré-visualização)** .
1. Selecione o fluxo de IU que quer editar.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Selecione **Editar**. 
1. Selecione **Novo passo**.

   ![Novo passo](../media/edit-desktop/new-step.png "Novo passo")

1. Selecione **Gravar aplicação** na lista de ações.

   ![Gravar aplicação](../media/edit-desktop/select-record-ui-actions.png "Gravar aplicação")

1. Selecione **Iniciar gravador**.

   ![Selecionar Iniciar gravador](../media/create-windows-ui-flow/select-launch-recorder.png "Selecionar iniciar gravador")

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
| Enviar teclas           | Envie teclas e combinações de teclas, como CTRL + C.                             |
| Clicar com o botão esquerdo do rato          |                                                                   |
| Obter texto            | Leia o texto de um elemento da interface de utilizador e, em seguida, utilize-o como uma saída. |
| Introduzir texto          |                                                                   |
| Obter elemento ativado | Verifique se um elemento da interface de utilizador está ativado ou desativado.         |
| Limpar elemento       | Limpe o valor num elemento da interface de utilizador editável.             |
| Aguardar alguns segundos    | Aguarde antes de continuar para o próximo passo.                           |

Siga estes passos para adicionar uma ação manual:

1. Inicie sessão no [Power Automate](https://flow.microsoft.com).
1. Selecione **Os meus fluxos** > **Fluxos de IU (pré-visualização)** .
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

Terá de fornecer os dados para os campos **elemementStack** e **elementXPath** do elemento do seletor.

Veja a seguir um exemplo do possível aspeto do **elemementStack**.

![Pilha de elementos](../media/edit-desktop/elementstack.png "Pilha de elementos")

Pode capturar o **elementXPath** com o [Gravador de IU WinAppDriver](https://blogs.windows.com/windowsdeveloper/2018/06/20/introducing-winappdriver-ui-recorder/).

![Ferramenta WAD](../media/edit-desktop/wad-tool.png "Ferramenta WAD")

Remova o primeiro elemento (tudo antes de /Window) antes de utilizar o resultado no **elementXPath** do seletor.

Teste o fluxo de IU para confirmar se o seletor funciona corretamente.

## <a name="use-advanced-controls"></a>Utilizar controlos avançados

Pode incorporar controlos avançados como **condições**, **alternar casos** e ações para **terminar** nos seus fluxos de IU.

Pode realizar estas operações avançadas ao realizar os seguintes passos num fluxo de IU existente.

1. Selecione o fluxo de IU que criou > **Mais comandos** (...) > **Editar**.

1. Selecione **+**  > **Adicionar uma ação** na seta para baixo do passo do fluxo de IU ao qual pretende adicionar uma lógica.

   ![Adicionar uma ação](../media/edit-desktop/add-action.png)

1. Selecione **Incorporado** e, em seguida, selecione uma das ações de controlo disponíveis.

   ![Incorporado](../media/edit-desktop/select-built-in.png)

1. Complete a expressão que precisa de ser avaliada. Pode utilizar conteúdo dinâmico e expressões para avaliar a condição e alternar os controlos. Adicionalmente, pode utilizar qualquer saída que seja criada pelos passos anteriores do fluxo de IU.

   ![Cartão de condição](../media/edit-desktop/condition-card.png)


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




## <a name="next-steps"></a>Próximos passos

- Saiba como [executar o fluxo de IU](run-ui-flow.md) que acabou de editar.

- Se quiser fazer mais com os fluxos de IU, poderá também experimentar os fluxos de IU com parâmetros de [entrada e saída](inputs-outputs-web.md).

