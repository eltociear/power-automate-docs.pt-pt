---
title: Criar fluxos que publicam cartões adaptáveis no Microsoft Teams | Microsoft Docs
description: Aprenda a criar fluxos para publicar conteúdos com formatação avançada com cartões adaptáveis no Microsoft Teams.
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
ms.date: 01/04/2020
ms.author: deonhe
ms.openlocfilehash: 186526427d8de7ee05dd6860e302faae5ac1d97f
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297434"
---
# <a name="create-your-first-adaptive-card"></a>Criar o primeiro cartão ajustável

Os cartões adaptáveis no Power Automate podem partilhar blocos de informações ou recolher dados através de um formulário para uma determinada origem de dados. 

Em qualquer dos casos, terá de esboçar os conjuntos de dados que irá partilhar e/ou os dados que o formulário terá de recolher. 

>[!TIP]
>Utilize blocos de dados simples em vez de matrizes de tabelas complexas.

## <a name="prerequisites"></a>Pré-requisitos

<!-- Is it still called Flow App? -->
- Microsoft Teams com a aplicação Flow instalada.

## <a name="add-an-action"></a>Adicionar uma ação

Neste procedimento, vai adicionar uma ação que utilizará os dados das ações anteriores no fluxo para publicar informações num canal do Microsoft Teams.

1. Iniciar sessão no Power Automate.
1. Selecione **Os meus fluxos** na barra de navegação superior.
1. Selecione **Novo** > **Instantâneo do zero**.
1. Atribua um nome ao seu fluxo.
1. Selecione **Acionar manualmente um fluxo** como acionador.
1. Selecione **Criar**.

    <!-- | [./media/image5.png](./media/image5.png) | [./media/image6.png](./media/image6.png) | -->

1. Selecione **Novo Passo**.
1. Procure **Microsoft Teams** e, em seguida, selecione **Publicar um cartão adaptável num canal do Teams e aguardar resposta** como ação.
1. Selecione a **Equipa** e o **Canal** no qual quer publicar o cartão.
1. Cole este JSON na caixa **Mensagem**.

    ``` JSON
    {
        "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
        "type": "AdaptiveCard",
        "version": "1.0",
        "body": [
            {
                "type": "TextBlock",
                "text": "Poll Request",
                "id": "Title",
                "spacing": "Medium",
                "horizontalAlignment": "Center",
                "size": "ExtraLarge",
                "weight": "Bolder",
                "color": "Accent"
            },
            {
                "type": "TextBlock",
                "text": "Header Tagline Text",
                "id": "acHeaderTagLine",
                "separator": true
            },
            {
                "type": "TextBlock",
                "text": "Poll Header",
                "weight": "Bolder",
                "size": "ExtraLarge",
                "spacing": "None",
                "id": "acHeader"
            },
            {
                "type": "TextBlock",
                "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer vestibulum lorem eget neque sollicitudin, quis malesuada felis ultrices. ",
                "id": "acInstructions",
                "wrap": true
            },
            {
                "type": "TextBlock",
                "text": "Poll Question",
                "id": "acPollQuestion"
            },
            {
                "type": "Input.ChoiceSet",
                "placeholder": "Select from these choices",
                "choices": [
                    {
                        "title": "Choice 1",
                        "value": "Choice 1"
                    },
                    {
                        "title": "Choice 2",
                        "value": "Choice 2"
                    },
                    {
                        "title": "Choice 3",
                        "value": "Choice 3"
                    }
                ],
                "id": "acPollChoices",
                "style": "expanded"
            }
        ],
        "actions": [
            {
                "type": "Action.Submit",
                "title": "Submit",
                "id": "btnSubmit"
            }
        ]
    }
    ```

1. Faça as seguintes substituições no JSON.

    >[!IMPORTANT]
    >Não remova as aspas ao fazer as substituições. Pode rever as escolhas do automóvel conforme as suas necessidades:

    Texto a alterar | Novo texto
    ------|------
    Texto da Linha de Etiqueta do Cabeçalho|Consultar o Power Automate
    Cabeçalho da Sondagem| Modelo de Automóvel Preferencial
    | Pergunta da Sondagem   | Vote no seu modelo de automóvel preferido nas opções listadas aqui. 
    Substitua o texto em latim por um motivo, ou contexto empresarial, relacionado com o motivo pelo qual está a realizar a sondagem.      |  Estamos a fazer uma sondagem aos nossos colaboradores para determinar se devemos fornecer locais de estacionamento personalizados dimensionados para os automóveis mais populares. 
    | Opção 1 (substituir em ambos os locais)  | Tesla   |
    | Opção 2 (substituir em ambos os locais) | Lexus |
    | Opção 3 (substituir em ambos os locais) | Honda |

1. Selecione **Novo Passo** e, em seguida, procure e selecione uma das ações **Enviar e-mail** às quais tem acesso. 
1. Forneça o destinatário do e-mail como a pessoa que selecionou o botão instantâneo (utilize a etiqueta **E-mail** do conteúdo dinâmico do **acionador**).
1. Configure o **Corpo** do e-mail da seguinte forma. Substitua as palavras entre chavetas “{}” por tokens dinâmicos:  
    **A sua resposta à sondagem foi {acPollChoices}** (acPollChoices é o conteúdo dinâmico da ação aguardar resposta).  **Foi submetida por {Nome de Utilizador}** (Nome de Utilizador é o conteúdo dinâmico do acionador)

## <a name="test-your-adaptive-card"></a>Testar o cartão ajustável

Para testar o seu trabalho, execute o fluxo que criou anteriormente e confirme o seguinte:

- A execução do fluxo não apresentou erros e aguarda pela resposta ao mostrar o indicador de espera da ação do Cartão Ajustável no ecrã de execução. 

- O canal do Teams tem o novo cartão ajustável publicado.

- Quando responder ao cartão ao selecionar um modelo de automóvel e ao selecionar o botão **Submeter** na secção inferior do cartão ajustável:

    - Não deverão ocorrer erros no cartão ajustável.

    - A execução do fluxo é concluída com êxito.

- A substituição do cartão será relevante após a submissão se tiver configurado a área **Atualizar mensagem** na parte inferior das ações **Aguardar resposta** (mostradas junto ao cartão de substituição correspondente). Caso contrário, todas as submissões irão simplesmente repor o formulário.

    ![Cartão de substituição](./media/adaptive-cards/update-message-2.png)

- A notificação por e-mail contém o corpo que mostra quem submeteu a resposta e qual o automóvel selecionado.

Parabéns! Acabou de criar o seu primeiro cartão ajustável interativo!

![Primeiro cartão concluído](media/adaptive-cards/finished-first-card.png) 


## <a name="troubleshooting-tips-for-adaptive-cards"></a>Sugestões para resolver problemas de cartões ajustáveis

Problemas mais comuns que encontrará ao criar cartões ajustáveis:

-   Os erros de execução de fluxos são geralmente causados por um dos seguintes fatores:

    -  A Aplicação Flow não está instalada no Microsoft Teams – [Instale a aplicação Flow](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams) no Teams. 
    
    Neste caso, o erro pode ser semelhante à seguinte captura de ecrã:  

    ![Mensagem de erro](media/adaptive-cards/error-message.png)

    -  JSON formatado incorretamente – normalmente, não é tão complexo quanto o esperado. Em geral, são apenas situações em que:

        - Existem aspas curvas ou aspas em falta nos valores do JSON. Verifique sempre o JSON para assegurar que todos os valores de texto e números estão entre aspas. Todas as aspas devem ser retas e não curvas.

        - Pode validar o formato do JSON ao colá-lo no [Card Payload Editor](https://adaptivecards.io/designer/).

    - URLs de Imagens em Falta – todos os valores das imagens nos Cartões Ajustáveis devem referir-se a um URL válido. O conteúdo de imagem completo não é suportado diretamente num Cartão Ajustável. Teste as ligações das imagens ao colar o URL no browser para ver se é apresentada uma imagem.

- Os Cartões Ajustáveis podem não ter o aspeto esperado devido a restrições de estilo e esquema:

    - Verifique se os valores de marcador de posição, os estilos de texto e a linguagem de markup cumprem os requisitos do esquema de Cartões Ajustáveis (reveja as **Melhores práticas do esquema para Cartões Ajustáveis** [aqui](https://adaptivecards.io/explorer/))

    - Tire partido do validador de Cartões adaptáveis do **Visual Studio Code**. Para o instalar a partir da aplicação Visual Studio Code, abra o Marketplace de Extensões e procure **Visualizador de Cartões adaptáveis**.

      ![Extensão do Visual Studio Code](media/adaptive-cards/visual-studio-code-extension.png)
  
Captura de ecrã truncada da extensão do Visualizador de Cartões adaptáveis instalada no Visual Studio Code (atalho: Ctrl+V+A depois de ativado).

- Os erros após a submissão do Cartão Ajustável devem-se geralmente à:

    - Utilização de uma ação que não inclui “aguardar resposta” no nome  
        
        ![Repetir](media/adaptive-cards/try-again.png)

    - Tentativa de submeter o cartão mais de uma vez. Cada Cartão Ajustável só pode ser submetido uma vez e todas as submissões adicionais serão ignoradas.
