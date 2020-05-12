---
title: Descrição Geral de Cartões Ajustáveis do Teams | Microsoft Docs
description: Saiba como utilizar os Cartões adaptáveis com o Microsoft Teams.
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
ms.date: 01/01/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7b39474bbc59ba059fd73f2edc7f9b5750edbec2
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298314"
---
# <a name="overview-of-adaptive-cards-for-microsoft-teams"></a>Descrição geral dos Cartões adaptáveis do Microsoft Teams

<br>
<iframe width="1129" height="635" src="https://www.youtube.com/embed/FqQ3jM2qPRM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


Os Cartões adaptáveis são um método independente de plataforma para partilhar e apresentar blocos de informações sem a complexidade da personalização de CSS ou HTML para os compor. Cria Cartões Ajustáveis no formato JSON, com integrações que as aplicações e serviços cloud podem trocar de forma aberta. Quando fornecido a um anfitrião específico, como o Microsoft Teams, o JSON é transformado numa IU nativa que se adapta automaticamente ao anfitrião. Assim, os designers de processos podem agora fornecer padrões de IU consistentes sempre que precisarem de apresentar informações como parte de um processo/automatização empresarial.
 
Como os Cartões adaptáveis se adaptam ao anfitrião, são veículos perfeitos para partilhar informações entre o Microsoft Teams e outros serviços.

  ![Captura de ecrã de Cartões Ajustáveis](media/adaptive-cards/multi-adaptive-cards.png)
 
## <a name="currently-available-actions-for-flows"></a>Ações atualmente disponíveis para os fluxos
 
As ações seguintes permitem aos criadores criar Cartões adaptáveis para o Microsoft Teams. À medida que os cenários de integração evoluem, outros anfitriões também serão suportados pelo Power Automate, que expandirá as suas oportunidades para tirar partido dos Cartões adaptáveis nas subscrições de cloud da Microsoft.
 
## <a name="directing-content-to-teams-members-or-aad-users"></a>Direcionar o conteúdo para os **membros do Teams ou utilizadores do AAD**
 
- **Publicar o seu próprio cartão ajustável como bot do Flow para um utilizador**  
  Esta ação publica um cartão ajustável como um bot do Flow para um utilizador específico. Neste caso, terá de fornecer o endereço de e-mail do destinatário e o cartão será apresentado nos feeds de chat e/ou de atividade do destinatário durante a execução do fluxo. Não existe nenhum requisito para que o utilizador faça parte de uma instância do Teams para receber estes tipos de Cartões Ajustáveis. Neste caso, apenas os botões de URL funcionam ao redirecionar para o URL configurado no fluxo.

    ![Exemplos de cartões ajustáveis](media/adaptive-cards/top.png)
 
- **Publicar um cartão ajustável como bot do Flow para um utilizador do Teams e aguardar resposta**  
  Esta ação publica um cartão ajustável como bot do Flow para um utilizador específico, como o caso apresentado anteriormente neste artigo. No entanto, neste caso, a execução do fluxo não continuará após a publicação até que o destinatário responda às entradas necessárias no cartão. O fluxo continua depois da resposta do destinatário. O fluxo devolve conteúdo dinâmico de uma (1) resposta por destinatário e por cartão.
 
## <a name="directing-content-to-teams-channels"></a>Direcionar o conteúdo para os **canais do Teams**
 
- **Publicar o seu próprio cartão ajustável como bot do Flow num canal**  
  Esta ação publica um cartão ajustável como um bot do Flow num canal do Teams específico. Nesse caso, ser-lhe-á pedido para fornecer a instância do Teams e um canal onde o cartão possa ser publicado. O criador do fluxo terá de ter acesso à instância do Teams para publicar um cartão ajustável aí. Neste caso, apenas os botões de URL funcionam ao redirecionar para o URL configurado no fluxo.
 
- **Publicar um cartão ajustável como bot do Flow num canal do Teams e aguardar resposta**  
  Esta ação publica um cartão ajustável como um bot do Flow num canal do Teams específico, tal como no caso acima. No entanto, neste caso, o fluxo não continuará até que alguém no canal responda a quaisquer entradas necessárias no cartão. O fluxo continuará assim que alguém no canal do Teams responda, mas apenas devolverá conteúdo dinâmico de uma (1) resposta por destinatário e por cartão.
 
     ![](media/adaptive-cards/bottom.png)

     >[!TIP]
     >Quando utilizar este cartão, o fluxo aguarda uma resposta de qualquer membro do Teams.
 
 
## <a name="known-issues"></a>Problemas conhecidos
 
- Não é possível recolher dados de Cartões Ajustáveis, a menos que sejam criados com uma das ações “aguardar resposta”. Os Cartões Ajustáveis que não aguardam devolvem um erro para todas as ações de botões, exceto OpenURL. Saiba mais em [Botões OpenURL](https://adaptivecards.io/explorer/Action.OpenUrl.html). 

- A seleção de botões Action.Submit num cartão que não inclui o sufixo “aguardar resposta” gerará um erro.
 
- Os Cartões Ajustáveis criados com as ações “aguardar resposta” só podem ser submetidos uma vez por cartão. A execução do fluxo continuará após a primeira resposta e quaisquer outras submissões serão ignoradas.
 
- Apenas as informações na caixa de entrada “Atualizar mensagem” (ver imagem 3) serão mostradas no cartão de substituição depois de os consumidores submeterem o cartão.

  Estarão disponíveis detalhes adicionais, como o ID de utilizador da pessoa que submete o cartão, no conteúdo dinâmico nas ações após a ação “aguardar resposta”. No entanto, pode ser necessário incluir o conector Utilizadores do Office 365 para completar as informações de perfil desejadas do utilizador que submeteu o cartão.
 
- Depois de os Cartões Ajustáveis “aguardar resposta” serem submetidos, o cartão é reposto e, em seguida, aparece exatamente igual, a menos que a área da mensagem de substituição/atualização esteja configurada. As mensagens de atualização são uma prática recomendada para atualizar outras, mas também para impedir que os consumidores tentem submeter o cartão mais de uma vez.
 
   ![Atualizar mensagem](media/adaptive-cards/update-message.png) 
 
>[!TIP]
>As entradas **Atualizar Mensagem** e **Deve atualizar o cartão** terão de ser configuradas se desejar um cartão de substituição.
 
- O Power Automate utiliza as funcionalidades e serviços exclusivos dos Cartões adaptáveis da Microsoft para processar os cartões em qualquer anfitrião. Este artigo destina-se a esclarecer as especificidades relacionadas com ações de fluxo. Também pode utilizar a documentação completa para [criar Cartões Ajustáveis](https://docs.microsoft.com/adaptive-cards/).
 
## <a name="learn-more"></a>Mais Informações 
 
- [Criar o primeiro cartão ajustável](https://docs.microsoft.com/power-automate/create-adaptive-cards)
- Documentação completa para o [conector do Microsoft Teams](https://docs.microsoft.com/connectors/teams/)
- Documentação completa sobre [E/S de Cartões Ajustáveis](https://docs.microsoft.com/adaptive-cards) 

