---
title: A aplicação móvel do Power Automate agora suporta a Gestão de Aplicações Móveis do Microsoft Intune. | Microsoft Docs
description: A aplicação móvel do Power Automate agora suporta a Gestão de Aplicações Móveis do Microsoft Intune.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 521876e669e87c40f6108c46d7e4e0aee962ca34
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297544"
---
# <a name="power-automate-mobile-app-supports-microsoft-intune"></a>A aplicação móvel do Power Automate suporta o Microsoft Intune


A aplicação móvel do Power Automate para iOS e Android suporta a Gestão de Aplicações Móveis (MAM) do Intune sem a inscrição de dispositivos. A MAM permite que os administradores de TI criem e imponham políticas de dados móveis para salvaguardar os dados organizacionais.

## <a name="why-intune-support-is-important"></a>Importância do suporte para o Intune

As organizações estão à procura de mais controlo sobre os dados contidos nos dispositivos móveis dos funcionários. As organizações podem querer restringir a forma de movimentação desses dados para o dispositivo e garantir que os dados são removidos, no caso de o funcionário sair da organização.

## <a name="what-is-microsoft-application-management-mam"></a>O que é a Microsoft Application Management (MAM)

A MAM permite às organizações criar políticas que regem a forma como as aplicações são utilizadas num inquilino. Tais políticas incluem impor a encriptação dos dados da aplicação ao limitar a capacidade de copiar ou extrair dados apenas para aplicações aprovadas ou impor um PIN num dispositivo.

### <a name="prerequisites"></a>Pré-requisitos

- Uma [política de proteção de aplicações](https://docs.microsoft.com/intune/app-protection-policies) do Intune.
- Um grupo do Azure Active Directory (Azure AD).
- Portal da Empresa. Um dos principais benefícios da MAM é que os dispositivos não precisam de ser inscritos na MAM do Intune. Apenas precisa do Portal da Empresa, que está disponível na App Store e na Google Play Store.
- Versão 2.31.0 da aplicação móvel do Power Automate para iOS, Android ou Windows Phone.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Criar uma política de proteção de aplicações, atribuir aplicações à política, ajustar definições e adicionar utilizadores a um grupo do Azure AD

Para a aplicação móvel do Power Automate ser gerida, tem de:

1. Criar uma política de proteção de aplicações.
1. Atribuir a aplicação móvel do Power Automate à política de proteção de aplicações.
1. Atribuir as definições da política. Por exemplo, pode atribuir a política para exigir um PIN de acesso ao dispositivo móvel que executa a aplicação móvel do Power Automate.
1. Aplicar a política de proteção de aplicações a um grupo do Azure AD específico.
1. Adicionar todos os utilizadores aos quais se aplica a política de proteção de aplicações ao grupo do Azure AD.

Siga estes passos para criar uma [política de proteção de aplicações](https://docs.microsoft.com/intune/app-protection-policies) que exige que os utilizadores da aplicação móvel do Power Automate introduzam um PIN para poderem aceder à aplicação. 


## <a name="test-the-app-protection-policy"></a>Testar a política de proteção de aplicações

Depois de criar a política de proteção de aplicações e atribuir utilizadores ao grupo do Azure AD, está na altura de utilizar a aplicação móvel do Power Automate e confirmar se a política funciona.

Para confirmar se a política funciona, siga estes passos:

1. Instale a aplicação móvel do Power Automate num dispositivo cuja plataforma corresponda a uma das plataformas que definiu na política de proteção de aplicações.
1. Inicie sessão na aplicação móvel com uma conta incluída no grupo do Azure AD que restringe a utilização da aplicação móvel aos utilizadores que têm um PIN.

Em seguida, será solicitado que:
1. Instale o Portal da Empresa.
1. Defina o PIN, se ainda não tiver um PIN que cumpra os critérios da política de proteção de aplicações.


## <a name="learn-more"></a>Mais Informações

Saiba como criar uma [política de proteção de aplicações](https://docs.microsoft.com/intune/app-protection-policies).

