---
title: Resolução de problemas de um fluxo | Microsoft Docs
description: Resolva alguns dos motivos mais comuns que levam à falha dos fluxos
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/01/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: faa0b50a9a525d5abaa818d05be8a97e6ad6663b
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79192789"
---
# <a name="troubleshooting-a-flow"></a>Resolução de problemas de um fluxo


## <a name="repair-tips-in-email"></a>Sugestões de reparação no e-mail

As sugestões de reparação serão enviadas para os proprietários dos fluxos por e-mail sempre que um fluxo falhar. Estes e-mails com sugestões de reparação contêm comentários específicos e acionáveis sobre determinados erros. Por exemplo, um erro comum é configurar um fluxo que tenta obter o gestor de uma pessoa no Office 365, sem existir qualquer gestor configurado no Azure Active Directory (Azure AD). Se esta ou várias outras condições provocarem a falha do fluxo, receberá um e-mail com sugestões de reparação como este:

![Sugestões de reparação](media/fix-flow-failures/repair-tips-email.png)

O e-mail de sugestões de reparação contém as seguintes secções:

Nome|Descrição
---|---
Hora|Apresenta a hora em que fluxo falhou pela primeira vez.
O que aconteceu|Disponibiliza uma descrição do problema que causou a falha do fluxo.
Como corrigir|Disponibiliza sugestões para resolver o problema que causou a falha do fluxo.
Sugestões de Resolução de Problemas|Oferece detalhes, incluindo o número de vezes em que o fluxo falhou e uma ligação para repetir o fluxo com os mesmos dados de entrada.

Para corrigir os erros indicados, selecione **Corrigir o meu fluxo** e siga os passos no e-mail de sugestões de reparação.

Os e-mails de sugestões de reparação são opcionais. Se não quiser recebê-los, basta desativá-los no menu de propriedades do fluxo específico.

Se o fluxo falhar, também poderá resolver o problema diretamente no Power Automate.  Seguem-se alguns cenários comuns de falha e sugestões para os corrigir.

## <a name="identify-the-error"></a>Identificar o erro
Antes de poder corrigir um fluxo, tem de identificar o motivo da falha. Clique ou toque no ícone de notificações na parte superior do portal Web (ou abra o separador **Atividade** na aplicação móvel) e, em seguida, clique ou toque no seu fluxo na lista apresentada.

![Notificações](./media/fix-flow-failures/notifications-toolbar.png)

Os detalhes sobre o fluxo são apresentados e, pelo menos, um passo mostra um ícone de exclamação vermelho. Abra esse passo e consulte a mensagem de erro.

![Mensagem de erro](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Falhas de autenticação
Em muitos casos, os fluxos falham devido a um erro de autenticação. Se tiver este tipo de erro, a mensagem de erro contém **Não autorizado** ou aparece um código de erro **401** ou **403**. Normalmente, para corrigir um erro de autenticação, basta atualizar a ligação:

1. Na parte superior do portal Web, clique ou toque no ícone de engrenagem para abrir o menu **Definições** e, em seguida, clique ou toque em **Ligações**.
2. Desloque-se para a ligação a que se refere a mensagem de erro **Não autorizado**.
3. Junto à ligação, clique ou toque na ligação **Verificar palavra-passe** na mensagem sobre a ligação não ser autenticada.
4. Verifique as suas credenciais seguindo as instruções que aparecem, regresse à falha de execução do fluxo e, em seguida, clique ou toque em **Submeter novamente**.
   
    O fluxo já deverá ser executado conforme esperado.

## <a name="action-configuration"></a>Configuração da ação
Os fluxos também falham se uma definição numa ação do fluxo não funcionar conforme esperado. Neste caso, a mensagem de erro contém **Pedido incorreto** ou **Não encontrado**, ou aparece o código de erro **400** ou **404**.

A mensagem de erro deve especificar como corrigir a falha. Terá de clicar ou tocar no botão **Editar** e, em seguida, corrigir o problema dentro da definição do fluxo. Guarde o fluxo atualizado e, em seguida, clique ou toque em **Submeter novamente** para tentar executar novamente com a configuração atualizada.

## <a name="other-failures"></a>Outras falhas
Se aparecer o código de erro **500** ou **502**, a falha é temporária ou transitória. Clique ou toque em **Submeter novamente** para tentar o fluxo novamente.

## <a name="getting-help-from-support-or-the-community"></a>Obter ajuda do apoio ao cliente ou da comunidade

Quando precisar de ajuda, pode utilizar as nossas opções de **Ajuda Autónoma** ou pode **Pedir ajuda** a outras pessoas.

### <a name="self-help"></a>Autoajuda 

1. Aceda ao [site de suporte](https://flow.microsoft.com/support/).
1. Aceda à categoria **Ajuda Autónoma** e selecione uma das opções da ajuda autónoma.

    ![Secção Pedir ajuda. Contactar o suporte.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Pedir ajuda a outras pessoas

1. Aceda ao [site de suporte](https://flow.microsoft.com/support/).
1. Selecione **Contactar o suporte** na secção **Pedir ajuda**.
    
    ![Secção Pedir ajuda. Contactar o suporte.](media/fix-flow-failures/ask-for-help.png)

1. Preencha os campos **Tipo de problema**, **Categoria**e **Em que podemos ajudar** e, em seguida, selecione **Ver soluções**. 

1. Tenha em atenção que a secção **Soluções** é apresentada depois de selecionar **Ver soluções**. Esta contém uma lista de resultados que pode utilizar para ajudar a resolver o problema que está a enfrentar. 

    ![Detalhes da ajuda integrada](media/fix-flow-failures/integrated-helper-details.png)

Se precisar de ajuda sobre um problema, a nossa [Comunidade](https://go.microsoft.com/fwlink/?LinkID=787467) e a Microsoft poderão ajudar. 

