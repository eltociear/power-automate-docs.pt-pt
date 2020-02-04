---
title: Perguntas sobre faturação e medição | Microsoft Docs
description: Respostas às perguntas mais frequentes sobre a faturação e a medição no Power Automate
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 3ea993f30f34a9997a1a3a3580b0151e93223d7a
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74356789"
---
# <a name="billing-and-metering-questions"></a>Perguntas sobre faturação e medição
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este artigo responde às perguntas mais frequentes sobre a faturação e a medição no Power Automate.

>[!NOTE]
> O Power Apps e o Power Automate utilizarão um [novo modelo de licenciamento](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq) a partir de 1 de outubro de 2019. 

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>Onde posso saber que planos de preços estão disponíveis?

Veja a [página de preços](https://flow.microsoft.com/pricing/).

## <a name="where-can-i-find-out-what-my-plan-is"></a>Onde posso saber qual é o meu plano?

Veja a [página de preços](https://flow.microsoft.com/pricing/).

## <a name="how-do-i-switch-plans"></a>Como posso mudar de plano?

No menu de navegação superior, selecione **Saber mais** > **Preços** e selecione o plano para o qual pretende mudar.

![Saber mais > Preços](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>Como posso saber que quantidade já utilizei?

Se estiver num plano gratuito ou de avaliação, clique ou toque no ícone de engrenagem, na barra de navegação superior, para mostrar a utilização atual em relação ao seu plano. 

![Botão Definições](./media/billing-questions/settings.png)

Se estiver num plano pago, as execuções são obtidas de entre todos os utilizadores da sua organização. Estamos a trabalhar em funcionalidades que exponham a quota disponível e a utilização em toda a organização.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>O que acontece se a minha utilização exceder os limites?

O Power Automate limitará as execuções de fluxos.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>Onde posso encontrar mais informações sobre os limites de utilização?

Na [página de preços](https://flow.microsoft.com/pricing/), veja a secção **FAQ**.

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>O que acontece se tentar fazer execuções com demasiada frequência?

O seu plano determina a frequência com que os seus fluxos são executados. Por exemplo, podem ser executados de 15 em 15 minutos, se estiver no plano gratuito. Se um fluxo for acionado e ainda não tiverem passado 15 minutos desde a última execução, é colocado em fila até que esses 15 minutos tenham passado.

## <a name="what-counts-as-a-run"></a>O que conta como uma execução?

Sempre que um fluxo é acionado, através de um acionador automático ou iniciando-o manualmente, é considerado uma execução. As verificações de existência de novos dados não contam como execuções.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>Existem diferenças entre Contas Microsoft e contas escolares ou profissionais para a faturação?

Yes. Se iniciar sessão com uma Conta Microsoft (tal como uma conta que termine em @outlook.com ou em @gmail.com), só pode utilizar o plano gratuito. Para tirar partido das funcionalidades do plano pago, inicie sessão com um endereço de e-mail escolar ou profissional.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Estou a tentar fazer a atualização, mas foi-me dito que a minha conta não é elegível.

Para atualizar, utilize uma conta escolar ou profissional ou crie uma [conta de avaliação do Office 365](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/).

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Por que motivo fiquem sem execuções quando o meu fluxo só foi executado algumas vezes?

Alguns fluxos podem ser executados com mais frequência do que o esperado. Por exemplo, poderá criar um fluxo que lhe envia uma notificação push sempre que o seu gestor lhe enviar um e-mail. Esse fluxo tem de ser executado sempre que receber um e-mail (de qualquer pessoa), porque tem de verificar se o e-mail veio do seu gestor. Esta ação conta como uma execução.

Pode contornar este problema, colocando todos os filtros de que necessita no acionador. No exemplo de notificação push, expanda o menu **Opções Avançadas** e forneça o endereço de e-mail do seu gestor no campo **De**.

## <a name="other-limits-and-caveats"></a>Outros limites e advertências

* Cada conta pode ter um máximo de:
  * 250 fluxos.
  * 15 Conectores Personalizados.
  * 20 ligações por API e 100 ligações no total.
* Só pode instalar um gateway no ambiente predefinido.
* Determinados conectores externos, tais como o Twitter, implementam a limitação de ligação para controlarem a qualidade de serviço. Quando a limitação está em vigor, os seus fluxos irão falhar. Se os seus fluxos estão a falhar, reveja os detalhes da execução que falhou no histórico de execuções do fluxo.
