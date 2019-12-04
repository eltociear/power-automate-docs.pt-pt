---
title: Compilar um ciclo de aprovação com o Common Data Service | Microsoft Docs
description: Crie uma entidade, um fluxo e uma aplicação que funcionem em conjunto, para que os revisores possam aprovar ou rejeitar ficheiros adicionados ao Dropbox.
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
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: eab01a20f44f68a85601ff824175f1a506ebec87
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74361320"
---
# <a name="build-an-approval-loop-by-using-power-automate-and-the-microsoft-common-data-service"></a>Compilar um ciclo de aprovação através do Power Automate e do Microsoft Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
O Common Data Service pode fornecer-lhe uma forma de compilar fluxos que tenham informações armazenadas numa base de dados independente de um fluxo. O melhor exemplo disso passa-se com as aprovações. Se armazenar o estado da aprovação numa entidade, o fluxo poderá trabalhar no topo dela.

Neste exemplo, terá de criar um processo de aprovação que é iniciado quando um utilizador adiciona um ficheiro ao Dropbox. Quando o ficheiro é adicionado, aparecem informações acerca do mesmo numa aplicação, onde um revisor pode aprovar ou rejeitar as alterações. Quando o revisor aprova ou rejeita a alteração, é enviado um e-mail de notificação e os ficheiros rejeitados são eliminados do Dropbox.

Ao seguir os passos nesta secção, irá compilar:

* uma **entidade personalizada** que irá conter informações sobre cada ficheiro adicionado ao Dropbox e se o estado do ficheiro está aprovado, rejeitado, ou pendente.
* um **fluxo** que adiciona informações à entidade personalizada quando um ficheiro é adicionado ao Dropbox, envia correio quando o ficheiro é aprovado ou rejeitado e elimina ficheiros rejeitados. Estes passos demonstram como compilar esse fluxo do zero, mas pode criar um fluxo semelhante a partir de um modelo.
* uma **aplicação** na qual um revisor pode aprovar ou rejeitar ficheiros adicionados ao Dropbox. Vai utilizar o Power Apps para gerar esta aplicação automaticamente com base nos campos da entidade personalizada.

**Pré-requisitos**

* Inscreva-se no [Power Automate](sign-up-sign-in.md) e no [Power Apps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/).
* Criar ligações para o Dropbox e Outlook do Office 365, como descreve o tópico [Gerir as suas ligações](https://powerapps.microsoft.com/tutorials/add-manage-connections/).

## <a name="build-the-entity"></a>Compilar a entidade
1. Inicie sessão no [powerapps.com](https://make.powerapps.com).
2. Se não aparecer a barra de navegação à esquerda por predefinição, clique ou toque no ícone com três linhas horizontais no canto superior esquerdo.
   
    ![Abrir barra de navegação à esquerda](./media/common-data-model-approve/hamburger-icon.png)
3. Na barra de navegação à esquerda, clique ou toque em **Gerir**, e, em seguida, clique ou toque em **Entidades**.
   
    ![Gerir entidades](./media/common-data-model-approve/manage-entities.png)
4. Se lhe for solicitado, clique ou toque em **Criar a minha base de dados**.
   
    ![Criar base de dados](./media/common-data-model-approve/create-database.png)
5. Junto ao canto superior direito, clique ou toque em **Nova entidade**.
   
    ![Criar entidade](./media/common-data-model-approve/new-entity.png)
   
    Se a janela do navegador não estiver maximizada, este botão poderá aparecer num local diferente.
6. Em **Nome da entidade**, especifique um nome que não tenha espaços e que nenhuma outra entidade da base de dados tenha.
   
    Para seguir exatamente este exemplo, especifique **ReviewDropboxFiles**.
   
    ![Especifique o nome da entidade](./media/common-data-model-approve/entity-name.png)
7. Em **Nome a apresentar**, especifique um nome amigável.
   
    ![Especifique o nome a apresentar](./media/common-data-model-approve/display-name.png)
8. Clique ou toque em **Seguinte**.
   
    ![Botão Seguinte](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>Adicionar campos à entidade
1. Junto ao canto superior direito, clique ou toque em **Adicionar campo**.
   
    ![Adicionar campo](./media/common-data-model-approve/add-field.png)
2. Na linha em branco que é apresentada na parte inferior da lista de campos, defina as propriedades de um campo **Aprovador**. (À medida que define estas propriedades, pode mudar para a coluna seguinte ao premir a tecla Tab.)
   
   * Na coluna **Nome a Apresentar**, escreva **Aprovador**.
   * Na coluna **Nome**, escreva **ApproverEmail**.
   * Na coluna **Tipo** coluna, clique ou toque na opção **E-Mail**.
   * Na coluna **Obrigatório**, selecione a caixa de verificação.
     
     ![Campo aprovador](./media/common-data-model-approve/approver-field.png)
3. Na linha seguinte, defina as propriedades de um campo **Estado**:
   
   * Na coluna **Nome a Apresentar**, escreva **Estado**.
   * Na coluna **Nome**, escreva **Estado**.
   * Na coluna **Tipo**, clique ou toque na opção **Texto**.
   * Na coluna **Propriedades**, deixe o valor predefinido.
   * Na coluna **Obrigatório**, selecione a caixa de verificação.
     
     ![Campo estado](./media/common-data-model-approve/status-field.png)
4. Na linha seguinte, defina as propriedades de um campo **FileID**:
   
   * Na coluna **Nome a Apresentar**, escreva **Identificador do Ficheiro**.
   * Na coluna **Nome**, escreva **FileID**.
   * Na coluna **Tipo**, clique ou toque na opção **Texto**.
   * Na coluna **Propriedades**, deixe o valor predefinido.
   * Na coluna **Exclusivo**, selecione a caixa de verificação.
   * Na coluna **Obrigatório**, selecione a caixa de verificação.
     
     ![Campo FileID](./media/common-data-model-approve/fileid-field.png)
5. Junto do limite direito, clique ou toque nas reticências (…) para o campo **FileID** e, em seguida, clique ou toque em **Definido como Campo de Título**.
   
    ![Definir campo de título](./media/common-data-model-approve/set-title-field.png)
6. Junto ao canto inferior esquerdo, clique ou toque em **Criar**.
   
    ![Criar uma entidade](./media/common-data-model-approve/create-button.png)
7. (opcional) Quando a lista de entidades voltar a aparecer, maximize a janela do navegador, se ainda não estiver maximizada e, em seguida, clique ou toque no cabeçalho da coluna **Tipo**. A lista é ordenada com as entidades personalizadas, tal como a que acabou de criar, que aparece na parte superior.

## <a name="sign-in-and-create-a-flow"></a>Iniciar sessão e criar um fluxo
1. Abra o [portal do Power Automate](https://flow.microsoft.com).
2. Maximize a janela do navegador, caso ainda não esteja maximizada e, em seguida, clique ou toque em **Iniciar sessão** junto ao canto superior direito.
   
    ![Botão de início de sessão do Power Automate](./media/common-data-model-approve/signin-flow.png)
3. No menu superior à direita, selecione o ambiente no qual criou a base de dados em powerapps.com.
   
    **Nota**: Se não selecionar o mesmo ambiente, não verá a entidade.
4. Junto ao canto superior esquerdo, clique ou toque em **Meus fluxos**.
   
    ![Botão Meus fluxos](./media/common-data-model-approve/myflows-button.png)
5. Junto ao canto superior esquerdo, clique ou toque em **Criar novo fluxo**.
   
    ![Botão Criar novo fluxo](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>Iniciar quando é adicionado um ficheiro
1. Na caixa que contém **Procurar mais acionadores**, escreva ou cole **Dropbox**, e, em seguida, clique ou toque em **Dropbox - quando é criado um ficheiro**.
   
    ![Criar acionador](./media/common-data-model-approve/create-trigger.png)
2. Em **Pasta**, clique ou toque no ícone da pasta e, em seguida, procure a pasta onde serão adicionados ficheiros.
   
    ![Selecionar pasta](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>Adicionar dados à entidade
1. Clique ou toque em **Novo passo**, e, em seguida, clique ou toque em **Adicionar uma ação**.
   
    ![Adicionar uma ação](./media/common-data-model-approve/add-action.png)
2. Na caixa que contém **Pesquisar por mais ações**, escreva ou cole **Common Data Service** e, em seguida, clique ou toque em **Common Data Service - Criar objeto**.
   
    ![Criar um objeto no Common Data Service](./media/common-data-model-approve/cdm-create-object.png)
3. Em **A entidade**, escreva ou cole **Rever**, e, em seguida, clique ou toque em **Rever ficheiros do Dropbox**.
   
    ![Escolher a entidade](./media/common-data-model-approve/choose-entity-flow.png)
4. Em **Título**, clique ou toque na caixa e, em seguida, clique ou toque em **Nome de ficheiro** na lista de tokens de parâmetro para adicionar esse token ao campo.
   
    ![Adicionar token de nome de Ficheiro](./media/common-data-model-approve/add-filename-token.png)
5. Em **Aprovador**, escreva ou cole o endereço de e-mail da pessoa que vai rever os ficheiros.
   
    **Nota**: para facilitar o teste do fluxo, especifique o seu próprio endereço. Pode alterá-lo mais tarde, quando o fluxo estiver preparado para utilização real.
   
    ![Adicionar aprovador](./media/common-data-model-approve/add-approver.png)
6. Em **Estado**, escreva ou cole **Pendente**.
   
    ![Adicionar estado predefinido](./media/common-data-model-approve/add-default-status.png)
7. Em **Identificador do Ficheiro**, clique ou toque na caixa e, em seguida, clique ou toque em **Identificador do Ficheiro** na lista de tokens de parâmetro para adicionar esse token ao campo.
   
    ![Adicionar token do Identificador do ficheiro](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>Verifique se o ficheiro foi revisto
1. Sob a ação **Criar objeto**, clique ou toque em **Novo passo**, clique ou toque em **Mais**, e, em seguida, clique ou toque em **Adicionar um fazer até**.
   
    ![Adicionar fazer até](./media/common-data-model-approve/add-do-until.png)
2. No canto superior esquerdo da ação **Fazer até**, clique ou toque na caixa que contém **Escolher um valor**.
   
    ![Escolher um valor](./media/common-data-model-approve/choose-value.png)
   
    **Nota**: se a janela do navegador não estiver maximizada, clique ou toque na caixa superior que contém **Escolher um valor**.
3. Em **Saídas de Criar objeto**, clique ou toque em **Estado** para adicionar esse token de parâmetro ao campo.
   
    ![Adicionar token de Estado](./media/common-data-model-approve/add-status.png)
4. Abra a lista junto ao centro da ação **Fazer até** e, em seguida, clique ou toque em **não é igual a**.
   
    ![Especifique não é igual a](./media/common-data-model-approve/is-not-equal.png)
5. No canto superior direito da ação **Fazer até**, escreva ou cole **Pendente** na caixa que contém **Escolher um valor**.
   
    ![Especificar estado a observar](./media/common-data-model-approve/do-until-not-pending.png)
   
    **Nota**: se a janela do navegador não estiver maximizada, clique ou toque na caixa inferior que contém **Escolher um valor**.
6. Perto da parte inferior da ação **Fazer até**, clique ou toque em **Adicionar uma ação**.
   
    ![Adicionar ação dentro de um fazer até](./media/common-data-model-approve/add-action-in-dountil.png)
7. Na caixa que contém **Pesquisar por mais ações**, escreva **Common** e, em seguida, clique ou toque em **Common Data Service - Obter objeto**.
   
    ![Obter um objeto](./media/common-data-model-approve/get-object.png)
8. Em **O espaço de nomes**, clique ou toque na base de dados.
9. Em **A entidade**, escreva ou cole **Rever**, e, em seguida, clique ou toque em **Rever ficheiros do Dropbox**.
   
    ![Escolher entidade](./media/common-data-model-approve/choose-entity-flow.png)
10. Em **ID de objeto**, clique ou toque na caixa e, em seguida, clique ou toque no token de parâmetro **Identificador do ficheiro** para adicioná-lo ao campo.
    
     ![Adicionar identificador de objeto](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>Verifique se o item foi aprovado
1. Sob a ação **Fazer até**, clique ou toque em **Novo passo**, e, em seguida, clique ou toque em **Adicionar uma condição**.
   
    ![Adicionar condição](./media/common-data-model-approve/add-condition.png)
2. No canto superior esquerdo da condição, clique ou toque na caixa que contém **Escolher um valor**.
   
    ![Canto superior esquerdo da condição](./media/common-data-model-approve/condition-upper-left.png)
   
    **Nota**: se a janela do navegador não estiver maximizada, clique ou toque na caixa superior que contém **Escolher um valor**.
3. Em **Saídas de Obter objeto**, clique ou toque no token de parâmetro **Estado** para adicionar o token ao campo.
   
    ![Adicionar estado a condição](./media/common-data-model-approve/add-status-to-condition.png)
4. No canto superior direito da condição, escreva ou cole **Aprovado** na caixa que contém **Escolher um valor**.
   
    ![Verificar se o estado está definido como aprovado](./media/common-data-model-approve/status-equals-approved.png)
   
    **Nota**: se a janela do navegador não estiver maximizada, escreva ou cole **Aprovado** na caixa inferior que contém **Escolher um valor**.

## <a name="send-notification-mail"></a>Enviar e-mail de notificação
1. Em **Se Sim, não fazer nada**, clique ou toque em **Adicionar uma ação**.
   
    ![Se sim, adicionar uma ação](./media/common-data-model-approve/if-yes-action.png)
2. Na caixa que contém **Procurar mais ações**, escreva ou cole **enviar correio**, e, em seguida, clique ou toque em **Outlook do Office 365 - Enviar um e-mail**.
   
    ![Se sim, enviar correio](./media/common-data-model-approve/if-yes-send-mail.png)
3. Em **Para**, escreva ou cole o endereço da pessoa que pretende notificar quando um item for aceite.
   
    **Nota**: para facilitar o teste do fluxo, especifique o seu próprio endereço. Pode alterá-lo quando o fluxo estiver preparado para utilização real.
   
    ![Destinatário da aprovação](./media/common-data-model-approve/approval-recipient.png)
4. Em **Assunto**, clique ou toque na caixa e, em seguida, clique ou toque no token de parâmetro **Nome do ficheiro** para adicioná-lo ao campo.
   
    ![Especifique o nome do ficheiro como o assunto do e-mail](./media/common-data-model-approve/subject-is-file-name.png)
5. Em **Corpo**, escreva ou cole **O item foi aprovado.**
   
    ![Corpo do correio de aprovação](./media/common-data-model-approve/approval-body.png)
6. Em **Se não, não fazer nada**, repita os passos 1 a 5 deste procedimento, excluindo especificar o corpo da mensagem de e-mail como **O item foi rejeitado.**
   
    ![Corpo do correio de rejeição](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>Eliminar ficheiros rejeitados
1. Abaixo dos campos para o correio de rejeição, clique ou toque em **Adicionar uma ação**.
   
    ![Adicionar ação de eliminar](./media/common-data-model-approve/add-delete-action.png)
2. Na caixa que contém **Procurar mais ações**, escreva ou cole **Dropbox**, e, em seguida, clique ou toque em **Dropbox - Eliminar ficheiro**.
   
    ![Eliminar ficheiros do Dropbox](./media/common-data-model-approve/dropbox-delete-file.png)
3. Em **Ficheiro**, clique ou toque na caixa e, em seguida, clique ou toque no token de parâmetro **Identificador do ficheiro** para adicioná-lo ao campo.
   
    ![Identificar ficheiro a eliminar](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>Guardar o fluxo
1. Na parte superior do ecrã, escreva ou cole um nome para o fluxo que está a criar e, em seguida, clique ou toque em **Criar Fluxo**.
   
    ![Guardar fluxo](./media/common-data-model-approve/save-flow.png)
2. Clique ou toque em **Fechar** e, em seguida, clique ou toque em **Concluído**.
3. No Dropbox, adicionar, pelo menos, dois ficheiros à pasta que especificou: um para testar a aprovação e outro para testar a rejeição.

## <a name="build-the-app"></a>Compilar a aplicação
1. Inicie sessão no [powerapps.com](https://make.powerapps.com), e, em seguida, clique ou toque em **Nova aplicação** perto da parte inferior da barra de navegação à esquerda.
   
    ![Criar uma aplicação num navegador](./media/common-data-model-approve/new-app-button.png)
2. Na caixa de diálogo apresentada, clique ou toque na opção para abrir o Power Apps Studio para o Windows ou o Power Apps Studio para a Web.
3. Se abriu o Power Apps Studio para o Windows, clique ou toque em **Novo** na barra de navegação esquerda.
4. Em **Criar uma aplicação a partir dos dados**, clique ou toque em **Esquema do Telefone** no mosaico **Common Data Service**.
   
    ![Criar aplicação](./media/common-data-model-approve/afd-cdm.png)
5. Na caixa **Procurar**, escreva ou cole **Rever**.
   
    ![Procurar uma entidade](./media/common-data-model-approve/search-entities.png)
6. Em **Escolher uma entidade**, clique ou toque em **Rever Ficheiros do Dropbox**.
   
    ![Escolher uma entidade](./media/common-data-model-approve/choose-entity.png)
7. Junto ao canto inferior direito, clique ou toque em **Ligar**.
   
    ![Botão Ligar](./media/common-data-model-approve/connect-button.png)
8. Se aparecer o ecrã de abertura da visita guiada, faça a visita guiada para se familiarizar com o Power Apps (ou clique ou toque em **Ignorar**).
   
    ![Visita guiada](./media/common-data-model-approve/quick-tour.png)
   
    Pode sempre efetuar a visita guiada mais tarde clicando ou tocando no ícone do ponto de interrogação junto ao canto superior esquerdo e, em seguida, clicar ou tocar em **Fazer a visita guiada**.
9. (opcional) Perto da parte inferior do ecrã, arraste o controlo de deslize para aumentar a ampliação de modo a que seja mais fácil ver a aplicação.
   
    ![Controlar aplicação de zoom](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>Personalizar a aplicação
1. Na barra de navegação à direita, clique ou toque no esquema que inclui um cabeçalho e uma descrição.
   
    ![Botão Ligar](./media/common-data-model-approve/choose-layout.png)
2. No **BrowseScreen**, clique ou toque abaixo da barra de pesquisa para selecionar o controlo de caixa de texto maior.
   
    ![Selecionar cabeçalho](./media/common-data-model-approve/select-header.png)
3. No painel da direita, abra a lista inferior ao clicar ou tocar na seta para baixo.
   
    ![Abrir lista pendente](./media/common-data-model-approve/open-dropdown.png)
4. Na lista inferior, clique ou toque em **Título** para visualizar o nome do ficheiro dos ficheiros adicionados.
   
    ![Definir dados do cabeçalho](./media/common-data-model-approve/set-heading.png)
5. No painel da direita, abra a lista superior e, em seguida, clique ou toque em **Estado** para visualizar o estado de cada ficheiro.
   
    ![Definir dados do corpo](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>Testar a solução global
1. No Power Apps, abra o modo de Pré-visualização ao clicar ou tocar no botão reproduzir junto ao canto superior esquerdo.
   
    ![Abrir modo de Pré-visualização](./media/common-data-model-approve/open-preview.png)
2. Para o primeiro ficheiro da lista, clique ou toque na seta para visualizar detalhes sobre esse ficheiro.
   
    ![Abrir ecrã Detalhes](./media/common-data-model-approve/open-details.png)
3. No canto superior direito, clique ou toque no ícone do lápis para alterar os detalhes sobre o ficheiro.
   
    ![Abrir ecrã Editar](./media/common-data-model-approve/edit-record.png)
4. Na caixa **Estado**, escreva ou cole **Aprovado**.
   
    ![Aprovar um ficheiro](./media/common-data-model-approve/change-status.png)
5. No canto superior direito, clique ou toque no ícone da marca de verificação para guardar as alterações e voltar ao ecrã detalhes.
   
    ![Guardar alterações](./media/common-data-model-approve/save-record.png)
   
    Dentro de alguns minutos, irá receber um e-mail a indicar que o ficheiro foi aprovado.
6. No canto superior direito, clique ou toque no botão anterior para voltar ao ecrã procurar.
   
    ![Voltar ao ecrã procurar](./media/common-data-model-approve/back-arrow.png)
7. Para o outro ficheiro da lista, clique ou toque na seta para visualizar detalhes sobre esse ficheiro.
   
    ![Abrir ecrã Detalhes](./media/common-data-model-approve/open-details.png)
8. No canto superior direito, clique ou toque no ícone do lápis para alterar os detalhes sobre o ficheiro.
   
    ![Abrir ecrã Editar](./media/common-data-model-approve/edit-record.png)
9. Na caixa **Estado**, escreva ou cole **Rejeitado** (ou qualquer outra coisa, exceto **Aprovado**, incluindo **Approvado** ou **Aprovado**).
   
    ![Rejeitar ficheiro](./media/common-data-model-approve/reject-file.png)
10. No canto superior direito, clique ou toque no ícone da marca de verificação para guardar as alterações e voltar ao ecrã detalhes.
    
     ![Guardar alterações](./media/common-data-model-approve/save-record.png)
    
     Dentro de alguns minutos, irá receber um e-mail a indicar que o ficheiro foi rejeitado e o ficheiro será eliminado do Dropbox.

