---
title: Perguntas e Respostas sobre a inscrição no Flow na sua organização | Microsoft Docs
description: Perguntas e respostas comuns sobre licenças, administração e utilizadores que se inscrevem no Flow no seu inquilino do Office 365
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/05/2016
ms.author: stepsic
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: f1e3ab59ad135b47b79466e1bd4d7fec73139955
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79196078"
---
# <a name="flow-in-your-organization-qa"></a>O Flow na sua organização - Perguntas e Respostas

Este tópico descreve como os utilizadores na sua organização podem utilizar o Flow e como poderá controlar o serviço do Flow.

## <a name="signing-up-for-flow"></a>Inscrever-se no Flow
### <a name="what-is-power-automate"></a>O que é o Power Automate?
O Power Automate é um serviço cloud público que ajuda utilizadores individuais e equipas a configurar fluxos de trabalho automatizados entre as suas aplicações e serviços favoritos para sincronizar, obter notificações, recolher dados e muito mais. 

### <a name="how-do-people-sign-up-for-flow"></a>Como é que as pessoas se inscrevem no Flow?
Existem duas formas possíveis através das quais os utilizadores individuais podem inscrever-se no Flow através do portal Web:

#### <a name="option-1"></a>Opção 1
Qualquer pessoa pode inscrever-se ao aceder a [flow.microsoft.com](https://flow.microsoft.com), selecionar **Inscrever-se gratuitamente** e, em seguida, concluir o processo de inscrição do Flow através de [admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free) ou [signup.live.com](https://signup.live.com).

#### <a name="option-2"></a>Opção 2
Qualquer pessoa pode inscrever-se ao aceder a [flow.microsoft.com](https://flow.microsoft.com), selecionar **Iniciar sessão** com o respetivo e-mail escolar, profissional ou pessoal e aceitar os termos de utilização do Flow.    

Quando um utilizador na sua organização se inscreve no Flow com a Opção 2, será automaticamente atribuída a esse utilizador uma licença gratuita do Power Automate.

[Inscrição no Flow](sign-up-sign-in.md) inclui mais detalhes.

### <a name="what-is-the-power-automate-free-plan"></a>O que é o Plano Gratuito do Power Automate?

O Plano Gratuito do Power Automate serve apenas para efeitos de controlo. A respetiva ativação ou desativação não afeta a capacidade de um utilizador criar fluxos. Se desativar o Plano Gratuito do Power Automate, este será novamente ativado quando um utilizador iniciar sessão. Este é o comportamento esperado.

### <a name="can-i-block-another-person-from-signing-up-for-flow"></a>Posso bloquear outra pessoa de se inscrever no Flow?
O Power Automate é um serviço cloud público, pelo que qualquer pessoa no mundo pode inscrever-se e utilizá-lo para automatizar as tarefas diárias. Para utilizar o Power Automate, os utilizadores não precisam de cumprir requisitos especiais nem de ter uma conta do Office 365. Por este motivo, de momento, não existe nenhum mecanismo para impedir que outra pessoa utilize o Flow (qualquer pessoa no mundo pode utilizá-lo, independentemente do endereço de e-mail).

No entanto, se uma pessoa se inscrever no Power Automate, mas optar por não a suportar dentro da organização, esta não poderá, de forma alguma, implicar custos para a sua empresa. Quando um indivíduo se inscreve no Power Automate, a relação é entre essa pessoa e a Microsoft, que é como em muitos outros serviços cloud da Microsoft, tais como o Bing, o Wunderlist, o OneDrive ou o Outlook.com. A utilização individual do Power Automate não implica de forma alguma que o serviço seja fornecido pela sua organização.

Por fim, se a sua empresa quiser restringir a utilização de dados exclusivos da organização dentro do Power Automate, será possível fazê-lo através de políticas de Prevenção de perda de dados (DLP).

### <a name="how-can-people-gain-access-to-the-paid-features-of-power-automate"></a>Como é que as pessoas podem obter acesso às funcionalidades pagas do Power Automate?
Os utilizadores individuais podem obter acesso às funcionalidades pagas do Power Automate de três formas diferentes:

1. Podem inscrever-se individualmente numa avaliação de 90 dias gratuita com o Plano Flow 1 ou o Plano Flow 2
2. Pode atribuir-lhes uma licença do Flow no portal de administração do Office 365.
3. Foram atribuídos ao utilizador planos do Office 365 e do Dynamics 365 que incluem acesso ao serviço do Flow. Veja a [página de preços do Flow](https://flow.microsoft.com/pricing/) para a lista de planos do Office 365 e do Dynamics 365 que incluem capacidades do Flow.

### <a name="can-i-block-another-person-from-using-the-paid-features-of-flow"></a>Posso bloquear outra pessoa de utilizar as funcionalidades pagas do Flow?
Qualquer utilizador individual pode experimentar as funcionalidades pagas do Power Automate durante 90 dias sem incorrer em quaisquer custos. No entanto, pode gerir totalmente a atribuição de licenças pagas perpétuas no âmbito da organização através do portal de administração do Office 365.

À semelhança do que acontece com as ofertas gratuitas, se um indivíduo optar por se inscrever na versão de avaliação, cria-se uma relação direta entre o indivíduo e a Microsoft, não necessariamente apoiada pela sua empresa.

## <a name="administration-of-flow"></a>Administração do Flow
### <a name="why-has-the-flow-icon-appeared-in-the-office-365-app-launcher"></a>Porque é que o ícone do Flow é apresentado no iniciador de aplicações do Office 365?
Como comunicado em agosto, agora, o Power Automate é uma parte fundamental do conjunto de aplicações do Office 365. Três meses após este anúncio, o Power Automate foi ativado como um serviço como parte do todos os SKUs existentes do Office 365. Como os utilizadores de todo o mundo podem agora utilizar o Power Automate este passou a ser apresentado no iniciador de aplicações.

Consulte a secção seguinte se quiser remover o mosaico do Flow do iniciador de aplicações por predefinição.

### <a name="how-do-i-remove-power-automate-from-the-app-launcher-for-my-organization"></a>Como posso remover o Power Automate do iniciador de aplicações da minha organização?
Se tiver sido atribuído a um utilizador uma licença Plano Flow 1 ou Plano Flow 2, pode realizar os passos seguintes para remover a licença do Flow desse utilizador, o que resultará na remoção do ícone do Flow do iniciador de aplicações:

1. Aceda ao [Portal de Administração do Office 365](https://portal.microsoftonline.com/).
2. Na barra de navegação à esquerda, selecione **Utilizadores** e, em seguida, selecione **Utilizadores Ativos**.
3. Encontre o utilizador do qual quer remover a licença e, em seguida, selecione o nome do mesmo.
4. No painel de detalhes de utilizador, na secção **Licenças de produtos**, selecione **Editar**.
5. Localize a licença denominada **Plano 1 do Power Automate** ou **Plano 2 do Power Automate**, defina o botão de alternar como **Desativado** e, em seguida, selecione **Guardar**.
   
   ![](./media/organization-q-and-a/remove-license.png)

Se um utilizador tem acesso ao Flow através da respetiva licença do plano do Office 365 e do Dynamics 365, pode desativar o acesso às funcionalidades adicionais que estão incluídas neste plano através dos seguintes passos:

1. Aceda ao [Portal de Administração do Office 365](https://portal.microsoftonline.com/).
2. Na barra de navegação à esquerda, selecione **Utilizadores** e, em seguida, selecione **Utilizadores Ativos**.
3. Encontre o utilizador a quem pretende remover o acesso e, em seguida, selecione o respetivo nome.
4. No painel de detalhes do utilizador, na secção **Licenças de produto**, selecione **Editar**.
5. Expanda a licença do Office 365 ou do Dynamics 365 do utilizador, desative o acesso ao serviço denominado **Flow para o Office 365** ou **Flow para o Dynamics 365** e, em seguida, selecione **Guardar**.
   
   ![](./media/organization-q-and-a/remove-service-plan.png)

A remoção em massa de licenças também é possível através do PowerShell. Veja [Remove licenses from user accounts with Office 365 PowerShell (Remover licenças de contas de utilizador com o Office 365 PowerShell)](https://technet.microsoft.com/library/dn771774.aspx) para obter um exemplo detalhado.   Por fim, pode encontrar mais orientações sobre a remoção em massa de serviços dentro de uma licença em [Desativar o acesso a serviços com o Office 365 PowerShell](https://technet.microsoft.com/library/dn771769.aspx).

A remoção da licença ou do serviço do Flow de um utilizador da sua organização resultará na remoção do ícone do Flow das seguintes localizações para esse utilizador:

1. [Office.com](https://office.com)
   
   ![](./media/organization-q-and-a/office-home.png)
2. Iniciador de Aplicações do Office 365
   
   ![](./media/organization-q-and-a/office-waffle.png)

Tenha em atenção que esta ação irá remover apenas o mosaico do Flow por predefinição. Um utilizador ainda pode optar por utilizar o Power Automate como utilizador individual.

### <a name="why-did-10000-licenses-for-power-automate-show-up-in-my-office-365-tenant"></a>Por que motivo são apresentadas 10 000 licenças do Power Automate no meu inquilino do Office 365?
Qualquer pessoa pode experimentar o Plano 1 ou o Plano 2 do Power Automate durante 90 dias e estas licenças de avaliação representam a capacidade disponível para novos utilizadores do Flow no seu inquilino. Não existem encargos para estas licenças. Especificamente, existem duas razões possíveis porque poderá ver uma capacidade de 10 000 licenças (de avaliação) do Flow no portal de administração do Office 365:

1. Se, pelo menos, um utilizador no seu inquilino tiver participado na pré-visualização pública do Flow de abril de 2016 a outubro de 2016, verá 10 000 licenças identificadas como “Microsoft Power Apps e Fluxos lógicos”
   
    ![](./media/organization-q-and-a/licenses2.png)
2. Se, pelo menos, um utilizador no seu inquilino se tiver inscrito numa versão de avaliação do Plano 2 do Flow através da **Opção 1** da inscrição de avaliação descrita na secção [Como podem os utilizadores inscrever-se no Power Apps](#how-do-people-sign-up-for-flow), verá 10 000 licenças com o nome “Microsoft Power Apps e Flow”
   
    ![](./media/organization-q-and-a/licenses1.png)

Pode optar por atribuir pessoalmente licenças adicionais aos utilizadores através do portal de administração do Office 365, mas tenha em atenção que se tratam de licenças de avaliação do Plano 2 do Power Automate e que expirarão no prazo de 90 dias após a atribuição a um utilizador.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>É gratuito? Ser-me-á cobrado algum valor por estas licenças?
Nenhum utilizador pode implicar qualquer custo para a sua organização sem o seu consentimento expresso, o que significa que as licenças gratuitas e as licenças de avaliação não podem causar quaisquer encargos para a sua organização. Para além disso, também não utilizam quaisquer quotas, tais como quotas de execução.

### <a name="i-removed-the-power-automate-free-license-and-users-can-still-access-flow"></a>Posso remover a licença gratuita do Power Automate e os utilizadores continuarem a ter acesso ao Flow?
A licença gratuita do Power Automate está incluída apenas para efeitos de controlo. Conforme explicado na primeira secção, não é possível impedir que outra pessoa utilize o Power Automate para fins individuais. Assim, a presença de uma licença gratuita do Power Automate não garante nem remove quaisquer capacidades.

### <a name="why-cant-i-see-all-flow-licenses-in-the-office-365-admin-portal"></a>Por que motivo não consigo ver todas as licenças do Flow no portal de Administração do Office 365?
Os utilizadores podem utilizar o Power Automate individualmente ou como parte da sua organização. Licenças ao nível da organização vão ser sempre visíveis no portal do Office 365. No entanto, se um utilizador se inscreve para obter uma avaliação como sendo individual, então não vai ser gerida pelo seu administrador do Office 365 e não vai ser apresentado no portal.

### <a name="how-does-an-individual-find-out-what-plan-they-are-on"></a>Como é que uma pessoa sabe em que plano se encontra?
Qualquer pessoa pode ver o plano que tem ao visitar a página de preços do Flow em [https://flow.microsoft.com/pricing](https://flow.microsoft.com/pricing). O plano ou versão de avaliação em que se encontram atualmente vai ser mostrado aqui.

### <a name="will-power-automate-sign-up-impact-the-identities-in-my-organization"></a>A inscrição no Power Automate afeta as identidades na minha organização?
Se a sua organização já tiver um ambiente do Office 365 existente e todos os utilizadores na sua organização tiverem contas do Office 365, a gestão de identidades não é afetada.

Se a sua organização já tem um ambiente existente do Office 365, mas nem todos os utilizadores na sua organização têm contas do Office 365, então vamos criar um utilizador no inquilino e atribuir licenças com base no endereço de e-mail escolar ou profissional do utilizador. Isto significa que o número de utilizadores que está a gerir a qualquer momento irá aumentar, à medida que os utilizadores na sua organização se inscrevem para o serviço.

Se a sua organização não tem um ambiente do Office 365 ligado ao seu domínio de e-mail, não há nenhuma alteração na forma como gere a identidade. Os utilizadores serão adicionados a um novo diretório de utilizadores apenas na cloud e terá a opção de assumir o controlo como administrador de inquilinos e de os gerir.

### <a name="a-new-tenant-was-created-by-power-automate-how-do-i-manage-this"></a>O Power Automate criou um novo inquilino. Como o posso gerir?
Se o Power Automate tiver criado um novo inquilino, poderá reivindicar e gerir esse inquilino com os seguintes passos:

1. Inscreva o inquilino ao inscrever-se no Flow com um domínio de endereço de e-mail que corresponda ao domínio do inquilino que pretende gerir. Por exemplo, se a Microsoft tiver criado o inquilino contoso.com, associe o inquilino com um endereço de e-mail que termine em @contoso.com.
2. Reclame o controlo de administração ao verificar a propriedade de domínio: assim que estiver no inquilino, pode promover-se para a função de administrador ao verificar a propriedade do domínio. Para o fazer, siga estes passos:    
   
   1. Aceda a [https://admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free).
   2. Selecione o ícone do iniciador de aplicações na parte superior esquerda e escolha Administrador.
   3. Leia as instruções na página **Tornar-se o administrador** e, em seguida, escolha **Sim, pretendo ser o administrador**.  
      
       **NOTA**: se esta opção não aparecer, significa que já foi implementado um administrador do Office 365.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Se tiver vários domínios, posso controlar os utilizadores que são adicionados ao inquilino do Office 365?
Se não realizar nenhuma ação, é criado um inquilino para cada domínio e o subdomínio de e-mail do utilizador.

Se pretender que todos os utilizadores estejam no mesmo inquilino, independentemente das extensões de endereço de e-mail:  

* Crie um inquilino de destino com antecedência ou utilize um inquilino existente. Adicione todos os domínios existentes e os subdomínios que pretende que sejam consolidados nesse inquilino. Em seguida, todos os utilizadores com endereços de e-mail que terminem nesses domínios e subdomínios são automaticamente associados ao inquilino de destino quando se inscreverem.

**IMPORTANTE:** não existe qualquer mecanismo automatizado suportado para mover utilizadores entre inquilinos depois de serem criados. Para saber mais sobre como adicionar domínios a um único inquilino do Office 365, veja [Adicionar os utilizadores e o domínio ao Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7).

### <a name="how-can-i-restrict-my-users-ability-to-access-my-organizations-business-data"></a>Como posso restringir a capacidade de acesso dos meus utilizadores aos dados de negócio da organização?
O Power Automate permite-lhe criar zonas de dados para dados de negócio e outros dados, conforme mostrado abaixo. Assim que estas políticas de prevenção de perda de dados são implementadas, os utilizadores são impedidos de estruturar ou executar o Flow para combinar dados de negócio e outros dados. Para obter mais detalhes, veja [Políticas de prevenção de perda de dados (DLP)](prevent-data-loss.md).

  ![](./media/organization-q-and-a/data-loss-prevention-policy.png)

