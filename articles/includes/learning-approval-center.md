Num tópico anterior, vimos como potencializar o feed do Twitter com uma lista do SharePoint de uma forma simples. Neste tópico, irá aprender a criar um cenário mais empresarial com as aprovações. Desta forma, qualquer pessoa com acesso à lista do SharePoint pode contribuir com tweets e a equipa de redes sociais pode aprovar ou rejeitar esses tweets. A equipa mantém o controlo da conta e do conteúdo que segue para os clientes. 

## <a name="create-an-approval-request-flow"></a>Criar um fluxo de pedido de aprovação
1. Na homepage do **Power Automate**, selecione **Aprovações**, selecione **Criar fluxo de aprovação**, desloque-se para baixo e selecione o modelo **Publicar itens de lista no Twitter após a aprovação**. 
   
    ![Selecionar modelo](./media/learning-approval-center/create-approval.png)
2. Verifique as credenciais da conta para o **SharePoint**, para as **Aprovações** e para o **Twitter**, e selecione **Continuar**. 
   
    ![Verificar credenciais](./media/learning-approval-center/verify-credentials.png)

Por predefinição, este modelo inicia um processo de aprovação sempre que é criado um novo item numa lista específica e, se o item for aprovado, publica um tweet no Twitter. Neste tópico, irá modificar este processo através da adição de passos que atualizam a lista do SharePoint com a resposta de aprovação, indicam se o tweet foi ou não aprovado e adicionam quaisquer comentários que o aprovador possa ter adicionado ao tweet proposto. 

1. Na lista **Tweets da Contoso** do SharePoint que criou anteriormente, adicione duas novas colunas:
   
   1. Selecione o sinal de adição "**+**" e selecione **Sim/Não**
   2. Introduza **ApprovalStatus** e selecione **Criar**
   3. Selecione o sinal de adição "**+**" e selecione **Linha de texto única**
   4. Introduza **ApproverComments** e selecione **Guardar**
      
      ![Adicionar colunas](./media/learning-approval-center/new-columns.png)
2. No **Power Automate**, na ação **Quando é criado um novo item**, introduza os seguintes valores:
   
   * **Endereço do Site**: o URL do SharePoint da sua equipa
   * **Nome da Lista**: ContosoTweets
     
     ![Site e lista](./media/learning-approval-center/site-address.png)
3. Na ação **Iniciar uma aprovação**, selecione **Editar** para apresentar todos os campos. 
   
    ![Editar campos](./media/learning-approval-center/edit-all-fields.png)
4. No **Título**, introduza **Novo tweet para** e selecione **Título** na lista de conteúdo dinâmico. 
   
    ![Título](./media/learning-approval-center/tweet-title.png)
5. Em **Atribuído a**, introduza e selecione o seu nome ou um nome de utilizador de teste. 
   
    ![Atribuído a](./media/learning-approval-center/tweet-assigned-to.png)
6. Em **Detalhes**, remova os itens predefinidos e adicione **TweetContent**, **TweetDate** e **Created by DisplayName** na lista de conteúdo dinâmico, ligados pelas palavras **em** e **por**. 
   
    ![Detalhes](./media/learning-approval-center/tweet-details.png)
7. Em **Ligação para o Item**, copie e cole o URL da sua lista do SharePoint e, em **Descrição da Ligação para o Item**, introduza **Lista de Tweets da Contoso**. 
   
    ![Ligação para o item](./media/learning-approval-center/tweet-item-link.png)
8. Na ação **Condição**, paire sobre a caixa **SE SIM**, selecione o sinal de adição "**+**" e selecione **Adicionar uma ação**. 
   
    ![Adicionar uma ação](./media/learning-approval-center/add-an-action.png)
9. Procure **atualizar item**, selecione o conector do **SharePoint** e selecione a ação **SharePoint – Atualizar item**.
   
    ![Atualizar item do SharePoint](./media/learning-approval-center/update-item.png)
10. No **Endereço do Site** e **Nome da Lista**, introduza o URL do site e a lista **ContosoTweets** novamente, e em **ID**, introduza o **ID** da lista de conteúdo dinâmico. 
    
     ![Site, lista e ID](./media/learning-approval-center/address-list-id.png)
11. Selecione o campo **Título** e, na lista de conteúdo dinâmico, procure **Título**. Adicione o item **Título** da ação **Quando é criado um novo item**. 
    
     ![Novo título](./media/learning-approval-center/add-title.png)
12. Selecione **ApprovalStatus** e defina o valor para **Sim**, selecione **ApproverComments** e defina o valor para **Comentários** da lista de conteúdo dinâmico. 
    
     ![Estado e comentários](./media/learning-approval-center/approver-status.png)
13. Junto à parte inferior da caixa **SE NÃO, NÃO FAZER NADA**, selecione **Adicionar uma ação**.
    
     ![Adicionar uma ação Não](./media/learning-approval-center/add-a-no-action.png)
14. Com os mesmos passos que utilizou para a configuração **SE SIM**, crie uma ação **SharePoint – Atualizar item** e configure os campos com os mesmos valores, mas desta vez defina **Estado da Aprovação** como **Não**. 
    
     ![Estado = não](./media/learning-approval-center/status-no.png)
15. Selecione a ação **Publicar um tweet**, selecione **Editar** e defina **Texto do tweet** como **Conteúdos do Tweet** na lista de conteúdos dinâmicos.  Na parte superior da página, selecione **Criar fluxo** para guardar o seu trabalho. 
    
     ![Publicar e guardar](./media/learning-approval-center/post-tweet.png)

Esta é apenas uma forma através da qual o Power Automate pode aumentar a produtividade da sua equipa. A equipa pode contribuir com ideias, notícias relevantes ou orientações sobre produtos, e você mantém o controlo sobre os tweets enviados para os clientes.

No tópico seguinte, iremos ver como pode ser quando um aprovador recebe um novo pedido para um tweet proposto. 

