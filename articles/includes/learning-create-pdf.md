Neste tópico, irá ver como a Contoso Flooring utiliza o Power Automate para converter automaticamente documentos para um formato padrão e os armazena no SharePoint Online para salvaguarda na cloud. Irá criar um fluxo que deteta quando um novo ficheiro foi adicionado a uma pasta do OneDrive para Empresas, converte esse ficheiro em PDF e armazena-o numa pasta do SharePoint Online. 

## <a name="prerequisites"></a>Pré-requisitos
Para este cenário, precisa de uma conta do **Muhimbi**, um serviço de conversão de PDFs. Se ainda não tiver uma conta do Muhimbi, pode inscrever-se numa [avaliação de 30 dias gratuita](http://www.muhimbi.com/Products/PDF-Converter-for-SharePoint/Products-PDF-Converter-for-SharePoint-Free-Trial.aspx). Siga as instruções nessa página para implementar a aplicação através do seu site do SharePoint Online. 

## <a name="create-the-source-and-target-folders"></a>Criar as pastas de origem e destino
Em primeiro lugar, terá de criar as pastas de origem e destino no OneDrive para Empresas e no SharePoint Online. 

1. No OneDrive para Empresas, em **Ficheiros**, crie uma pasta com o nome **Documentos Concluídos**. 
   
    ![](./media/learning-create-pdf/onedrive-folder.png)
2. No SharePoint Online, em **Documentos Partilhados**, crie uma pasta com o nome **PDF – Ficheiros concluídos**. 
   
    ![](./media/learning-create-pdf/sharepoint-folder.png)

## <a name="create-the-flow"></a>Criar o fluxo
1. No Power Automate, selecione **Os Meus Fluxos** e selecione **Criar do zero**. 
   
    ![](./media/learning-create-pdf/create-blank-flow.png)
2. Selecione **Procurar entre centenas de conectores e acionadores**.
3. Procure **OneDrive**, selecione **OneDrive para Empresas** e, em seguida, selecione o acionador **OneDrive para Empresas - Quando um ficheiro é criado**. Em **Pasta**, selecione o ícone de pasta e selecione a pasta **Documentos Concluídos** que criou no passo anterior. 
   
    ![](./media/learning-create-pdf/onedrive-trigger.png)
4. Selecione **Novo passo** e, em seguida, selecione **Adicionar uma ação**. 
   
    ![](./media/learning-create-pdf/new-action.png)
5. Procure **Muhimbi**, selecione o conector **Muhimbi PDF** e selecione a ação **Muhimbi PDF – Converter documento**.
   
    ![](./media/learning-create-pdf/muhimbi-action.png)
6. Neste momento, o Power Automate poderá solicitar que efetue a autenticação no Muhimbi. Terá de registar o Muhimbi com o **ID do inquilino SharePoint** para que o Power Automate utilize o serviço Muhimbi. 
   
   1. Para localizar o ID do inquilino, selecione o ícone de engrenagem **Definições** no SharePoint Online e selecione **Definições de sites**.
   2. Em **Administração de Coleções de Sites**, selecione **Permissões de aplicações da coleção de sites**. O seu ID do inquilino é o identificador após o símbolo "**@**" numa das listagens da aplicação. 
      
       ![](./media/learning-create-pdf/tenant-id.png)
7. Na ação **Converter documento**, defina os seguintes valores:
   
   * **Nome do ficheiro de origem**: na lista de conteúdo dinâmico, selecione **Nome de ficheiro**.
   * **Conteúdo do ficheiro de origem**: na lista de conteúdo dinâmico, selecione **Conteúdo de ficheiro**.
   * **Formato de saída**: no menu pendente, selecione **PDF**.
     
     ![](./media/learning-create-pdf/muhimbi-configuration.png)

Até ao momento, configurou o fluxo com os seguintes passos: 

1. O fluxo é acionado sempre que é adicionado um novo ficheiro a uma pasta específica do OneDrive para Empresas. 
2. O serviço Muhimbi converte esse ficheiro em PDF. 

No passo final, irá adicionar uma ação que irá mover o documento PDF para uma pasta do SharePoint Online na qual a equipa pode ter acesso ao mesmo.  

1. Selecione **Novo passo** e, em seguida, selecione **Adicionar uma ação**.  Procure **SharePoint** e selecione a ação **SharePoint – Criar ficheiro**. 
   
    ![](./media/learning-create-pdf/sharepoint-create-file.png)
2. Na ação **Criar ficheiro**, defina os seguintes valores:
   
   * **Endereço do site**: o URL do seu site do SharePoint.  
   * **Caminho da pasta**: selecione o ícone de pasta e navegue para a pasta **PDF - Ficheiros concluídos**.
   * **Nome de ficheiro**: na lista de conteúdos dinâmicos para **Converter documento**, selecione **Nome de ficheiro base** e adicione "**.pdf**" para que seja guardado no SharePoint com a extensão de ficheiro. 
   * **Conteúdo do ficheiro**: na lista de conteúdo dinâmico para **Converter documento**, selecione **Conteúdo do ficheiro processado**.
3. Selecione **Criar fluxo** na parte superior da página para guardar o seu trabalho.
   
    ![](./media/learning-create-pdf/sharepoint-configure-file.png)

## <a name="test-the-flow"></a>Testar o fluxo
1. Para testar o fluxo, adicione um novo ficheiro à pasta **Documentos Concluídos** no OneDrive para Empresas. 
2. No fluxo, selecione **Os meus fluxos** e selecione o novo fluxo para ver o histórico de execuções. Por predefinição, o fluxo está configurado para ser executado a cada cinco minutos. 
3. Depois de o fluxo ser executado, certifique-se de que o ficheiro foi convertido em PDF e guardado na pasta **PDF – Ficheiros concluídos** do SharePoint. 
   
    ![](./media/learning-create-pdf/test-the-flow.png)

