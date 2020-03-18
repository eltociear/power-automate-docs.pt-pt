---
title: Criar um fluxo com o Dynamics 365 (online) | Microsoft Docs
description: Criar fluxos de trabalho úteis com uma ligação do Dynamics 365 e do Power Automate
services: ''
suite: flow
documentationcenter: na
author: Mattp123
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/06/2017
ms.author: matp
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f341adb319c20a201525bb6b7a8a0c54e2da5ea3
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195043"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Criar um fluxo com o Dynamics 365 (online)

Ao utilizar um conector do Dynamics 365, pode criar fluxos que são iniciados quando ocorre um evento no Dynamics 365, ou noutro serviço qualquer, que, depois, realizam uma ação no Dynamics 365 ou nos outros serviços. 

No Power Automate, pode configurar fluxos de trabalho automatizados entre os seus serviços e aplicações favoritos para sincronizar ficheiros, receber notificações, recolher dados e mais. Para obter mais informações, veja [Introdução ao Power Automate](getting-started.md).

> [!IMPORTANT] 
> Para invocar um acionador de fluxo, a entidade do Common Data Service utilizada com o fluxo deve ter o **Controlo de Alterações** ativado. Mais informações: [Ativar a monitorização de alterações para controlar a sincronização de dados](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization). 

## <a name="create-a-flow-from-a-template"></a>Criar um fluxo a partir de um modelo
Pode utilizar um dos muitos modelos disponíveis para criar um fluxo, como, por exemplo:

* Quando é criado um objeto no Dynamics 365, crie um item de lista no SharePoint.
* Crie registos de oportunidades potenciais do Dynamics 365 a partir de uma tabela do Excel.
* Copie as contas do Dynamics 365 para os clientes no Dynamics 365 for Operations.

Para criar um fluxo a partir de um modelo, siga estes passos.

1. Inicie sessão no [site do Power Automate](https://flow.microsoft.com/).
2. Clique ou toque em **Serviços** e, em seguida, clique ou toque em **Dynamics 365**.
3. Estão disponíveis vários modelos. Para começar, selecione o modelo que pretende.

## <a name="create-a-task-from-a-lead"></a>Criar uma tarefa a partir de uma oportunidade potencial
Se não estiver disponível nenhum modelo para aquilo de que precisa, crie um a partir do zero. Estas instruções mostram-lhe como criar uma tarefa no Dynamics 365 sempre que é criada uma oportunidade potencial no mesmo.

1. Inicie sessão no [site do Power Automate](https://flow.microsoft.com/).
2. Clique ou toque em **Os meus fluxos** e, em seguida, clique ou toque em **Criar do zero**.
3. Na lista de acionadores de fluxos, clique ou toque em **Dynamics 365 - quando é criado um registo**.
4. Se lhe for pedido, inicie sessão no Dynamics 365.
5. Em **Nome da organização**, selecione a instância do Dynamics 365 onde pretende que o fluxo escute.
6. Em **Nome da entidade**, selecione a entidade que quer escutar, que funcionará como um acionador que vai iniciar o fluxo.
   
     Nestas instruções, selecione **Oportunidades potenciais**.
   
    ![Detalhes do fluxo](./media/connection-dynamics365/flow-details.png)
    > [IMPORTANTE] Para que o fluxo seja acionado na entidade do Dynamics 365, a definição da entidade tem de ter o **Controlo de Alterações** ativado. Veja [Ativar a monitorização de alterações para controlar a sincronização de dados](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization).
    
7. Clique ou toque em **Novo passo**, e, em seguida, clique ou toque em **Adicionar uma ação**.
8. Clique ou toque em **Dynamics 365 – criar um novo registo**.
9. Em **Nome da Organização**, selecione a instância do Dynamics 365 onde pretende que o fluxo crie o registo. Tenha em atenção que não tem de ser a mesma instância a partir da qual o evento é acionado.
10. Em **Nome da Entidade**, selecione a entidade que vai criar um registo quando o evento ocorre.
    
     Nestas instruções, selecione **Tarefas**.
11. Aparece uma caixa **Assunto**. Quando clica ou toca na mesma, aparece um painel de conteúdo dinâmico, onde pode selecionar um destes campos:
    
    * **Apelido**. Se selecionar este campo, o apelido da oportunidade potencial será inserido no campo **Assunto** da tarefa, quando é criada.
    * **Tópico**. Se selecionar este campo, o campo **Tópico** da oportunidade potencial será inserido no campo **Assunto** da tarefa, quando é criada.
    
    Nestas instruções, selecione **Tópico**.
    
    ![Tópico para adicionar fluxos](./media/connection-dynamics365/flow-addtopic.png)
    
    > **Sugestão:** no painel de conteúdo dinâmico, clique ou toque em **Ver mais** para apresentar mais campos associados à entidade. Por exemplo, também pode preencher o campo **Assunto** da tarefa com o campo **Nome da Empresa**, **Cliente**, **Descrição** ou **E-mail** da oportunidade potencial.
    > 
    > 
12. Clique ou toque em **Criar fluxo**.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Criar uma tarefa do Wunderlist a partir de uma tarefa do Dynamics 365
Estas instruções mostram-lhe como criar uma tarefa no [Wunderlist](https://www.wunderlist.com) sempre que é criada uma tarefa no Dynamics 365. O Wunderlist é um serviço baseado na Internet que pode ser utilizado para criar listas de tarefas, adicionar lembretes ou acompanhar recados.

1. Inicie sessão no [site do Power Automate](https://flow.microsoft.com/).
2. Clique ou toque em **Os meus fluxos** e, em seguida, clique ou toque em **Criar do zero**.
3. Na lista de acionadores de fluxos, clique ou toque em **Dynamics 365 - quando é criado um registo**.
4. Em **Nome da organização**, selecione a instância do Dynamics 365 onde pretende que o fluxo escute.
5. Em **Nome da Entidade**, selecione a entidade que quer escutar, que funcionará como um acionador que vai iniciar o fluxo.
   
    Nestas instruções, selecione **Tarefas**.
6. Clique ou toque em **Novo passo**, e, em seguida, clique ou toque em **Adicionar uma ação**.
7. Escreva *criar uma tarefa* e, em seguida, clique ou toque em **Wunderlist – criar uma tarefa**.
8. Em **ID da lista**, selecione **Caixa de Trabalho**.
9. Em **Título**, selecione **Assunto**, no painel de conteúdo dinâmico.
10. Clique ou toque em **Criar fluxo**.  

## <a name="trigger-based-logic"></a>Lógica baseada em acionadores
Acionadores como **Quando um registo é criado**, **Quando um registo é atualizado** e **Quando um registo é eliminado** iniciam o seu fluxo alguns minutos após a ocorrência do evento.  Em casos raros, o fluxo poderá demorar até duas horas a ser acionado.

Quando o acionador é processado, o fluxo recebe uma notificação, embora seja executado de acordo com os dados existentes no momento da execução da ação.  Por exemplo, se o fluxo for acionado quando um novo registo for criado e o utilizador atualizar o registo duas vezes antes da execução do fluxo, este será executado apenas uma vez com os dados mais recentes.

## <a name="specify-advanced-options"></a>Especificar opções avançadas
Quando adiciona um passo a um fluxo, pode clicar ou tocar em **Mostrar opções avançadas** para adicionar uma consulta de filtro ou de “ordenar por” que controle a forma como os dados são filtrados nesse fluxo.

Por exemplo, pode utilizar uma consulta de filtro para obter apenas contactos ativos, que pode ordenar por apelido. Para tal, introduza a consulta de filtro de OData **statuscode eq 1** e selecione **Apelido**, no painel de conteúdo dinâmico. Para obter mais informações sobre filtrar e ordenar por consultas, veja [MSDN: $filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) e [MSDN: $orderby](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2).

  ![Consulta orderby de fluxo](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Melhores práticas quando são utilizadas opções avançadas
Quando adiciona um valor a um campo, tem de corresponder o tipo de campo, independentemente de escrever um valor ou de o selecionar a partir do painel de conteúdo dinâmico.

| Tipo de campo | Como utilizar | Onde encontrar | Nome | Tipo de dados |
| --- | --- | --- | --- | --- |
| Campos de texto |Os campos de texto só requerem uma única linha de texto ou conteúdo dinâmico que seja um campo de tipo de texto. Os exemplos incluem os campos **Categoria** e **Subcategoria**. |**Definições** > **Personalizações** > **Personalizar o Sistema** > **Entidades** > **Tarefa** > **Campos** |**categoria** |**Linha de Texto Única** |
| Campos de número inteiro |Alguns campos requerem conteúdo de número inteiro ou dinâmico que seja um campo de tipo de número inteiro. Os exemplos incluem **Percentagem Concluída** e **Duração**. |**Definições** > **Personalizações** > **Personalizar o Sistema** > **Entidades** > **Tarefa** > **Campos** |**percentcomplete** |**Número Inteiro** |
| Campos de data |Alguns campos requerem uma data introduzida no formato dd/mm/aaaa ou conteúdo dinâmico que seja um campo de tipo de data. Os exemplos incluem **Criado Em**, **Data de Início**, **Início Real**, **Último Tempo de Suspensão**, **Fim Real** e **Data para Conclusão**. |**Definições** > **Personalizações** > **Personalizar o Sistema** > **Entidades** > **Tarefa** > **Campos** |**createdon** |**Data e Hora** |
| campos que requerem um ID de registo e um tipo de pesquisa |Alguns campos que fazem referência a outro registo de entidade requerem o ID do registo e o tipo de pesquisa. |**Definições** > **Personalizações** > **Personalizar o Sistema** > **Entidades** > **Conta** > **Campos** |**accountid** |**Chave Primária** |
|Conjunto de Opções|Os campos do Conjunto de Opções requerem que um valor inteiro conhecido seja transmitido para este tipo de campo.  Na área de personalização do Dynamics 365, pode ver o campo do valor inteiro subjacente aos conjuntos de opções, bem como a respetiva etiqueta.|Definições > Personalização > Personalizar o Sistema > Entidades > Conta > Campos | Método de Contacto Preferencial| Número Inteiro|

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Mais exemplos de campos que requerem um ID de registo e um tipo de pesquisa
Partindo da tabela anterior, eis mais exemplos de campos que não funcionam com valores selecionados na lista de conteúdo dinâmico. Em vez disso, estes campos requerem que sejam introduzidos o ID de registo e o tipo de pesquisa nos campos no Power Apps.

* **Proprietário** e **Tipo de Proprietário**.
  
  * O campo **Proprietário** tem de ser um ID de registo de utilizador ou de equipa válido.
  * **Tipo de Proprietário** tem de ser **systemusers** ou **teams**.
* **Cliente** e **Tipo de Cliente**.
  
  * O campo **Cliente** tem de ser uma conta ou um ID de registo de contacto válido.
  * **Tipo de Cliente** tem de ser **accounts** ou **contacts**.
* **Relativamente a** e **Tipo de Relativamente a**.
  
  * O campo **Relativamente a** tem de ser um ID de registo válido, como uma conta ou um ID de registo de contacto.
  * **Tipo de Relativamente a** tem de ser o tipo de pesquisa para o registo, como **accounts** ou **contacts**.

Este exemplo acrescenta um registo de conta que corresponde ao ID de registo, adicionando-o ao campo **Relativamente a** da tarefa.

  ![recordId e tipo de conta do fluxo](./media/connection-dynamics365/flow-recordid-account.png)

Este exemplo também atribui a tarefa a um utilizador específico com base no ID de registo do utilizador.

  ![recordId e tipo de utilizador do fluxo](./media/connection-dynamics365/flow-recordid-user.png)

Para localizar o ID de um registo, veja [Localizar o ID de registo](#find-the-records-id) mais adiante neste tópico.

> **Importante:** os campos não deverão conter nenhum valor se tiverem a descrição “Apenas para utilização interna”. Estes campos incluem **Caminho percorrido**, **Parâmetros Adicionais** e **Número da Versão da Regra de Fuso Horário.**
> 
> 

## <a name="find-the-records-id"></a>Localizar o ID do registo
1. Na aplicação Web do Dynamics 365, abra um registo, como um registo de conta.
2. Na barra de ferramentas de ações, clique ou toque em **isolar**
   ![destacar registo](./media/connection-dynamics365/popout.png) (ou clique ou toque em **ENVIAR UMA LIGAÇÃO POR E-MAIL** para copiar o URL completo para o seu programa de e-mail predefinido).
   
    Na barra de endereço do browser, o URL contém o ID de registo entre os carateres de codificação %7b e %7d.
   
   ![RecordId](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>Tópicos relacionados
[Troubleshooting a flow (Resolver problemas em fluxos)](fix-flow-failures.md)

[O Flow na sua organização - Perguntas e Respostas](organization-q-and-a.md)

[Perguntas mais frequentes](frequently-asked-questions.md)

