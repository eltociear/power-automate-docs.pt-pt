## <a name="what-is-an-environment"></a>Que é um ambiente:
Um ambiente é um espaço virtual utilizado para armazenar, gerir e partilhar aplicações, fluxos e dados de negócio no Common Data Service. Os ambientes são geolocalizados para que todas as aplicações e dados armazenados na base de dados de um ambiente estejam também geolocalizados.  

## <a name="terms-you-should-get-familiar-with"></a>Termos com os quais deverá familiarizar-se

| **Termo** | **Descrição** |
| --- | --- |
| **Centro de administração** |O centro de administração é um [portal Web](https://admin.flow.microsoft.com) para gerir todos os ambientes e políticas de prevenção de perda de dados. |
| **Common Data Service** |O Common Data Service permite-lhe adicionar armazenamento de dados e capacidades de modelação às aplicações. |
| **Funções de ambiente** |As duas funções de ambiente são Administrador do Ambiente e Criador do Ambiente. |
| **Funções de utilizador** |As duas funções de utilizador predefinidas são Utilizador da Organização e Proprietário da Base de Dados. Pode adicionar funções e associar permissões a essas funções. |

## <a name="purposes-for-an-environment"></a>Objetivos de um ambiente
Pode utilizar ambientes para:  

* Separe as aplicações, os fluxos e os dados de negócio com base em diferentes funções, requisitos de segurança ou utilizadores.  
* Separar aplicações, fluxos e dados de negócio com base na localização das equipas ou departamentos.
* Gerir ambientes de produção e teste.  

## <a name="how-to-use-environments"></a>Como utilizar ambientes
Os ambientes podem servir vários objetivos diferentes, dependendo das necessidades organizacionais, alguns exemplos são:  

* Pode optar por compilar todas as aplicações e fluxos num único ambiente. 
* Pode optar por criar um ambiente para diferentes tipos de aplicações e fluxos. Por exemplo, pode criar um ambiente de teste e um ambiente de produção.  
* Também pode optar por criar ambientes com base na estrutura organizacional ou mesmo com base na localização geográfica das suas equipas ou departamentos. Por exemplo, se tiver equipas na Austrália, no México e na Europa, pode criar um ambiente para cada um destes locais e geri-los de forma independente.  

**Tenha em atenção**: os ambientes não estão visíveis para os utilizadores, pelo que não precisam de preocupar-se em relação aos ambientes em que se encontram. Os ambientes são uma ferramenta para os administradores categorizarem, gerirem e partilharem aplicações e fluxos organizacionais.  

## <a name="what-are-roles"></a>O que são as funções?
Uma pessoa com acesso a um ambiente deve ter atribuída a função de **Administrador do Ambiente** ou de **Criador do ambiente**. Os administradores de ambiente podem efetuar todas as tarefas administrativas no ambiente. Um criador de ambiente pode criar recursos num ambiente existente. Um indivíduo pode ter ambas as funções simultaneamente.  

**Nota**: todos os utilizadores terão acesso a um ambiente predefinido quando for atribuído acesso ao Power Automate a cada um deles. Os utilizadores podem ter acesso a vários ambientes.  

## <a name="create-an-environment"></a>Criar um ambiente
Pode criar ambientes a partir do [Centro de administração do Power Automate](https://admin.flow.microsoft.com) com estes passos:  

1. Nomeie o ambiente.
2. Selecione uma região onde o ambiente será alojado.
3. Opcionalmente, pode optar por criar uma base de dados para o ambiente. Pode criar uma base de dados depois de criar um ambiente, se desejar.
4. Opcionalmente, selecione quem terá acesso à base de dados. Pode restringir ou dar acesso à base de dados a todos os utilizadores. 

## <a name="add-users-to-an-environment"></a>Adicionar utilizadores a um ambiente
Depois de criar um ambiente, pode adicionar utilizadores à função de Administrador do Ambiente ou à função de Criador do Ambiente. Tal como acontece com todas as outras tarefas administrativas, estas alterações são feitas a partir do centro de administração.  

Depois de ter criado o ambiente e de ter adicionado os utilizadores, pode ainda querer criar uma política de prevenção de perda de dados (DLP) para ajudar a gerir a utilização dos seus dados de negócio. Iremos abranger isso no tópico seguinte. 

