Neste tópico, irá aprender como **criar um fluxo de botão** para a empresa Contoso Flooring. 

Os fluxos de botão podem ser utilizados para **enviar um e-mail** para uma equipa e **alertá-la das tarefas** a efetuar. A **Propriedade** dos fluxos **pode ser atribuída a um** colaborador ou **partilhada por vários** membros da equipa.  

1. Em primeiro lugar, aceda ao [site do Power Automate](https://ms.flow.microsoft.com) e inicie sessão.
2. Após iniciar a sessão, selecione **Os Meus Fluxos** e **Criar do zero**.
   
    ![Criar do zero](./media/learning-create-button-flow/2-create-from-blank.png)
   
    A primeira coisa de que irá precisar é um acionador. Um fluxo de botão é um acionador de utilização prática. 
3. Se não tiver um na sua lista, selecione **Procurar entre centenas de conectores e acionadores** na parte inferior da página, introduza **botão**, e irá ser apresentado. 
4. Selecione **Botão de fluxo para dispositivos móveis**.
   
    ![Botão Procurar](./media/learning-create-button-flow/3-button-flow.png) 
5. Selecione **Botão de fluxo para dispositivos móveis - Acionar manualmente um fluxo**.
   
    ![Selecionar acionador manual](./media/learning-create-button-flow/4-press-it.png)
6. No ecrã de entrada, selecione **Adicionar texto de entrada**,
   
    ![Adicionar entrada](./media/learning-create-button-flow/5-add-input.png)
7. Introduza **Contoso Flooring** na primeira caixa de texto, e **E-mail de entrega no armazém** na segunda caixa de texto.
   
    ![Adicionar entrada](./media/learning-create-button-flow/6-text-for-flow.png)
8. Selecione **Novo passo**. 
   
    ![Texto de entrada](./media/learning-create-button-flow/7-input-description.png)
9. Selecione **Adicionar uma ação**. 
   
    ![Adicionar ação](./media/learning-create-button-flow/8-add-an-action.png)
10. Selecione o conector **Office 365 Outlook**. Se não o vir, procure **outlook**.
    
     ![Procurar o outlook](./media/learning-create-button-flow/9-search-outlook.png)
11. Selecione **Office 365 Outlook - Enviar um e-mail**.
    
     ![Enviar e-mail](./media/learning-create-button-flow/10-send-email.png)
    
     Quando o botão é premido, é enviado um e-mail a toda a equipa do Contoso Warehouse, independentemente da localização dos membros da equipa no edifício, permitindo-lhes saber que a entrega chegou.
12. Expanda os campos e personalize o e-mail de trabalho da Contoso Flooring.
    
    1. No campo **Para**, introduza um endereço de e-mail que seja válido na sua organização.
    2. No campo **Assunto**, introduza **Entrega Chegou**. 
    3. À direita, repare que apareceu uma caixa de **Conteúdo dinâmico**. Para mostrar, na linha do assunto, a data e hora exatas a que o botão foi premido, selecione **Data** e **Carimbo de data/hora**. 
       
        ![Data e hora de e-mail](./media/learning-create-button-flow/11-email-date-time.png)
13. Agora, introduza um **Corpo** simples no e-mail, descrevendo algo como **Membros da Equipa do Armazém, dirijam-se ao cais de descarga pois a entrega de hoje chegou**.
14. Selecione **Criar fluxo** para guardar o fluxo.
    
     ![Criar fluxo](./media/learning-create-button-flow/12-create-flow.png)

## <a name="create-a-team-flow"></a>Criar um fluxo de equipa
Pode utilizar este botão de fluxo como um exemplo para criar um fluxo de equipa. E se o criador deste fluxo estiver de baixa médica? E se essa pessoa sair da empresa? Quer certificar-se de que o fluxo se mantém operacional. Para tal, adicione coproprietários.

1. Selecione o **ícone de equipa** no fluxo para adicionar um coproprietário.
   
    ![Criar fluxo de equipa](./media/learning-create-button-flow/13-create-team-flow.png) 
2. Introduza nomes, endereços de e-mail ou grupos de utilizadores para adicionar coproprietários.
   
    ![Adicionar coproprietários](./media/learning-create-button-flow/14-add-co-owners.png)
3. Para remover os coproprietários, selecione o caixote do lixo à direita do nome deles.
   
    ![Remover os coproprietários](./media/learning-create-button-flow/15-remove-co-owners.png)
4. Selecione **Remover este proprietário** para concluir a remoção.
   
    ![Remover os coproprietários](./media/learning-create-button-flow/16-agree-to-remove.png)

## <a name="summary"></a>Resumo
Nesta lição, viu como **criar um fluxo de botão**. 

Em minutos, o fluxo permitiu que um colaborador do armazém pudesse **alertar a equipa** relativamente à **chegada de uma entrega**, para que a equipa não tivesse de ficar à espera e desperdiçasse tempo valioso que poderia ser gasto noutras tarefas. 

Em seguida, o colaborador partilhou esse botão com a equipa, para que outras pessoas pudessem acionar o mesmo fluxo na sua ausência.

## <a name="next-lesson"></a>Lição seguinte
Veja a lição seguinte para ver como criar um fluxo que utiliza **notificações push**.

