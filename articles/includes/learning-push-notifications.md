Neste fluxo, irá criar uma lista do **SharePoint** na qual a equipa de Marketing da **Contoso Flooring** armazena as **Publicações do Twitter** e datas de publicação da empresa. A partir daí, irá compilar um fluxo que irá publicar automaticamente Tweets do conteúdo. 

## <a name="connect-power-automate-services"></a>Ligar aos serviços do Power Automate
Neste tópico, irá utilizar os serviços do **SharePoint** e **Twitter**. Se estiver a utilizar um serviço que não conhece, primeiro terá de ligar ao novo serviço. 

1. No Power Automate, selecione o **ícone de engrenagem** e, em seguida, selecione **Ligações**.
   
    ![Obter ligação](./media/learning-push-notifications/2-get-connection.png) 
2. Selecione **+ Criar ligação**.
   
    ![Criar ligação](./media/learning-push-notifications/3-create-connection.png) 
3. Desloque para baixo na lista, localize o Twitter e selecione **+**.
   
    ![Clicar no sinal de adição](./media/learning-push-notifications/4-click-plus.png)
4. Para autorizar uma conta do Twitter, introduza o seu nome de utilizador ou o e-mail e a palavra-passe e, em seguida, selecione **Autorizar aplicação**.
   
    ![Criar ID e palavra-passe](./media/learning-push-notifications/5-create-id-pswd.png)
5. Para verificar as suas ligações, selecione o **ícone de engrenagem** e **Ligações**.
   
    ![As minhas ligações](./media/learning-push-notifications/6-my-connections.png)
   
    Deverá ver a nova ligação do Twitter e quaisquer outras ligações que criou. 
   
    ![Ligação do Twitter](./media/learning-push-notifications/7-twitter-connection.png)

## <a name="build-a-sharepoint-list"></a>Criar uma Lista do SharePoint
A primeira coisa a fazer é criar uma nova lista do SharePoint Online para a Contoso Flooring. 

1. No SharePoint Online, selecione **Nova** e, em seguida, **Lista**.
   
    ![Criar nova lista](./media/learning-push-notifications/1-new-list.png)
2. Dê à lista o nome **Tweets da Contoso**. 
3. Limpe a caixa de verificação **Mostrar na navegação do site** e selecione **Criar**.
   
    ![Criar lista](./media/learning-push-notifications/2-name-create-list.png)
   
    Ao selecionar **Criar**, o SharePoint direciona-o para a sua nova lista.
4. Por predefinição, a lista tem uma única coluna - **Título**. Adicione outra coluna e dê-lhe o nome **Conteúdos do Tweet**. Tudo o que escrever nos seus tweets irá para aqui. 
   
   1. Selecione o sinal de adição e selecione **Mais...**
      
       ![Criar lista](./media/learning-push-notifications/3-add-more-column-types.png)
   2. Selecione **Várias linhas de texto** e selecione **OK**.
      
       ![Criar lista](./media/learning-push-notifications/4-add-column.png)
5. Adicione uma coluna para a data e hora do tweet, e dê-lhe o nome **Data do Tweet**.
   
   1. Como fez em **Conteúdos do Tweet** acima, selecione o sinal de adição e selecione **Mais...**
      
       ![Coluna de data e hora](./media/learning-push-notifications/5-date-time-col.png)
   2. Desloque para baixo até **Formato de Data e Hora**. Selecione **Data e Hora**, para que ambas sejam incluídas.
      
       ![Data e hora](./media/learning-push-notifications/6-date-time-must-do.png)
   3. Selecione **OK**. Pode ver a lista **Tweets da Contoso** no seu site do SharePoint e pode adicionar novos itens à lista.

## <a name="build-the-flow"></a>Compilar o fluxo
A sua lista está criada, pode agora compilar o fluxo.

### <a name="choose-a-trigger"></a>Escolher um acionador
1. No Power Automate, aceda a **Os Meus Fluxos** e, em seguida, selecione **Criar do zero**.
   
    ![Criar do zero](./media/learning-push-notifications/8-create-from-blank.png)
2. Selecione **Quando um item é criado**.
   
    ![Adicionar acionador](./media/learning-push-notifications/9-add-trigger.png)
   
    Queremos que o nosso acionador dispare quando uma nova linha é adicionada com conteúdo do tweet.
3. Selecione o seu site do SharePoint e, em seguida, selecione a lista que configurou anteriormente, **Tweets da Contoso**.
   
    ![Novo item criado](./media/learning-push-notifications/11-set-trigger.png)

E fica assim explicado o acionador.

### <a name="add-an-action-to-delay-posting"></a>Adicionar uma ação para atrasar a publicação
1. Selecione **+ Novo passo** e selecione **Adicionar uma ação**. 
   
    ![Adicionar o passo e a ação](./media/learning-push-notifications/12-add-step-and-action.png)
2. No serviço **Agendamento**, selecione **Atraso até**. 
   
    ![Atraso até](./media/learning-push-notifications/13-delay-until-schedule.png)  
3. Defina o valor do atraso.
   
   1. Clique ou toque no **Carimbo de data/hora**. 
   2. Quando a caixa de conteúdo dinâmico for aberta, desloque-se para baixo para a parte inferior até encontrar as três colunas da lista do SharePoint: **Título**, **Data do Tweet** e **Conteúdo do Tweet**.
   3. Selecione **Data do Tweet**. 
      
       ![Atraso até carimbo de data/hora](./media/learning-push-notifications/14-delay-until-timestamp.png)
      
       Agora, quando alguém adicionar algo à sua lista do SharePoint, este irá atrasar qualquer ação até à data e hora definidas na coluna **Data do Tweet**.
      
       ![Carimbo de hora dinâmico](./media/learning-push-notifications/15-dynamic-timestamp.png)

### <a name="add-an-action-to-post-a-tweet"></a>Adicionar uma ação para publicar um Tweet
Irá agora adicionar outra ação para o fluxo fazer entre a data e hora especificadas na coluna **Data do Tweet**.

1. Selecione **+ Novo passo**, **Adicionar uma ação** e procure o **Twitter**.
   
    ![Adicionar tweet](./media/learning-push-notifications/16-add-tweet.png) 
2. Escolha a ação **Twitter - Publicar um tweet**.
   
    ![Publicar um tweet](./media/learning-push-notifications/17-post-tweet.png) 
3. Clique ou toque no campo **Texto do Tweet** e, na caixa de conteúdo dinâmico, selecione **Conteúdos do Tweet**. Segue-se a sequência que criou. 
   
    ![Conteúdo de data do Tweet](./media/learning-push-notifications/18-tweet-date-content.png)
4. Selecione **Criar fluxo...**.
   
    ![Criar fluxo](./media/learning-push-notifications/19-tiny-create.png) 
5. Selecione **Concluído**.
   
    ![Clicar em concluído](./media/learning-push-notifications/19-click-done.png)
   
    O fluxo está agora concluído.
   
    ![O fluxo está concluído](./media/learning-push-notifications/20-flow-is-done.png)
   
    Quando um novo item é criado na sua lista do SharePoint, o fluxo atrasa a publicação até à data predefinida. Quando essa data for atingida, o fluxo irá publicar no Twitter com o texto da coluna **Conteúdo do Tweet conteúdo** da lista.

## <a name="next-lesson"></a>Lição seguinte
Na lição seguinte, irá aprender a **executar fluxos com base no agendamento**, ao utilizar um acionador denominado **Periodicidade**.

