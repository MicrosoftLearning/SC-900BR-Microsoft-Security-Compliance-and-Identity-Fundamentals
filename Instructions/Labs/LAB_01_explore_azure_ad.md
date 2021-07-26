﻿---
lab:
    title: 'Explorar o Azure Active Directory'
    module: 'Módulo 2 Lição 1: Descrever as funcionalidades das soluções de Gerenciamento de Identidades e Acessos da Microsoft: Explorar os serviços e tipos de identidade do Azure AD'
---

# Laboratório: Explorar o Azure Active Directory

## Cenário do laboratório

Neste laboratório, você acessará o Azure Active Directory.  Além disso, você vai criar um usuário e configurar parâmetros diferentes, como a adição de licenças.  



**Tempo estimado**: 10-15 minutos

#### Tarefa 1:  Como assinante do Microsoft 365, você já está usando o Azure AD.  Nesta tarefa, você mostrará o acesso ao Azure AD usando o portal de administração do Microsoft 365 e o Portal do Azure.

1. Abra o Microsoft Edge.

2. Na barra de endereços, insira **admin.microsoft.com** para acessar o Centro de administração do Microsoft 365.

3. Entre com suas credenciais de administrador. 
    1. Na janela de logon insira **admin@WWLxZZZZZZ.onmicrosoft.com** (onde ZZZZZZ é seu ID de locatário exclusivo fornecido pelo seu provedor de hospedagem do laboratório) e clique em **Avançar**.
    1. Digite a senha do administrador, que deve ser fornecida pelo seu provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Se a opção para permanecer conectado for exibida, clique em **Sim**.

4. No painel de navegação esquerdo do Centro de administração do Microsoft 365, selecione **Mostrar tudo**.

5. Em Centros de administração, selecione **Azure Active Directory** (talvez seja necessário rolar a tela).  Uma nova página do navegador abre a página Meu painel do Centro de administração do Azure Active Directory. Na janela principal do painel, você verá diversos blocos, incluindo o de identidade da organização (Contoso, o locatário e a edição do Azure AD), um bloco para usuários e grupos, entre outros.

6. No painel de navegação à esquerda, na seção de favoritos, clique em **Azure Active Directory**.  Na janela principal, você verá outro painel de navegação que lista todos os serviços que estão disponíveis no Azure AD. À direita, você verá informações sobre o locatário da Contoso e links para os tipos de identidade que você pode criar, além de serviços em destaque.  

7. Agora, abra uma nova janela do navegador e, na barra de endereços, insira **portal.azure.com**.  Como você já está conectado como admin@WWLxZZZZZZ.onmicrosoft.com e usou essas mesmas credenciais para resgatar seu Azure Pass, é preciso entrar como administrador quando acessar o Portal do Azure.  Você pode verificar isso conferindo o email no canto superior direito da página e passando o mouse sobre o ícone de usuário.

8. A página de aterrissagem do Portal do Azure mostra os serviços do Azure, como Azure Active Directory, VMs, contas de armazenamento, bancos de dados e muito mais.  Selecione **Azure Active Directory**.  

9. Agora você está vendo o Azure Active Directory do locatário do Microsoft 365 da Contoso.    Seja qual for a abordagem usada para acessar os serviços do Azure Active Directory (o Portal de administração do Microsoft 365 ou o Portal do Azure), você acabará no mesmo lugar: o Azure Active Directory da Contoso, onde pode administrar todos os serviços do Azure AD.

10. Mantenha esta página do navegador aberta para a próxima tarefa.


#### Tarefa 2:  Nesta tarefa, você aprenderá a criar um novo usuário no Azure Active Directory e conhecerá alguns dos serviços que podem ser gerenciados no nível do usuário.

1. Acesse a guia Contoso – Microsoft Azure que está aberta no seu navegador. Se você tiver fechado a guia anteriormente, abra uma página do navegador e, na barra de endereços, digite portal.azure.com e selecione Azure Active Directory.  Você deve estar conectado como administrador no Portal do Azure. Se não estiver, entre novamente.

2. No painel de navegação à esquerda, selecione **Usuários**.  Veja que seu locatário já está configurado com usuários.

3. Na parte superior da página, selecione **+ Novo usuário**.

4. A opção **Criar usuário** já deve estar selecionada. Se não estiver, selecione-a.

5. Preencha os campos de **Identidade** da seguinte forma:

    1. Nome de usuário: **sara**.

    2. Campo nome: **Sara Perez**.

    3. Nome: **Sara**.

    4. Sobrenome: **Perez**.

6. Preencha os campos de **Senha** da seguinte forma:

    1. Clique em **Permita-me criar a senha**.

    1. Senha inicial: **Naja8996**. Quando Sara entrar pela primeira vez, ela receberá uma solicitação para alterar a senha.

7. Configure os **Grupos e funções**.

    1. Ao lado de Grupos, clique em **0 grupos selecionados**.  Isso exibe os grupos disponíveis.  Veja a lista de grupos disponíveis.

    2. Clique em **Operações** (talvez seja preciso rolar a página) e pressione **Selecionar**. Observe como o texto ao lado dos grupos foi atualizado para refletir que há um grupo selecionado.  

    3. Ao lado de funções, selecione **Usuário**. A lista de funções do Directory é exibida.  Role a tela para baixo para ver as diversas funções internas, mas não altere a função do usuário.  Feche essa janela clicando no **X** do canto superior direito da página.

8. Ajuste as **Configurações**

    1. Bloquear entrada:  **Não** (manter a configuração padrão).

    1. Localização de uso: **Estados Unidos** (clique no menu suspenso e depois role para baixo para encontrar essa opção).  A configuração do local de uso é obrigatória para atribuir licenças.

9. Na parte inferior da página, clique no botão **Criar**.

10. Verifique se o usuário aparece na lista (os nomes são listados em ordem alfabética).

11. Na lista de usuários, selecione o usuário que você acabou de criar, **Sara Perez**.  A página do perfil é aberta.

12. O painel de navegação à esquerda mostra as várias opções que podem ser configuradas para o usuário.  Selecione **Grupos**.  Aqui você pode ver mais informações sobre o grupo.  Verifique se o grupo Operações está listado (pode levar alguns minutos até que a atribuição de grupo seja exibida).  Observação:  você também verá o grupo Contoso, embora só tenhamos atribuído um grupo ao criar o usuário.  Isso é resultado de uma política pré-configurada no locatário, que atribui automaticamente os novos usuários ao grupo Contoso.

13. No painel de navegação à esquerda selecione **Licenças**.  Veja que não há nenhuma atribuição de licença para esse usuário.  

14. Para adicionar uma licença, clique em **+ Atribuições** na parte superior da janela principal.

15. Em Selecionar licenças, clique em **Office 365 E3** e **Windows 10 Enterprise E3**. Depois, clique no botão **Salvar** na parte inferior da tela. Uma notificação no canto superior direito da tela deve mostrar que a atribuição de licença foi bem-sucedida.

16. Clique no **X** no canto superior direito para fechar a janela de atribuição de licença.

17. Clique no **ícone Atualizar** na parte superior da página para confirmar a atribuição de licença.

18. Volte para a página de Visão geral do Azure Active Directory da Contoso clicando em **Contoso** no canto superior esquerdo da tela (a trilha), acima de onde está escrito Sara Perez | Licenças.

19. Você criou e configurou um usuário no Azure Active Directory com sucesso.

20.	Saia de todas as guias do navegador clicando no ícone do usuário ao lado do endereço de email, no canto superior direito da tela. Em seguida, feche todas as janelas do navegador.

#### Tarefa 3:  Nesta tarefa, você vai se conectar como Sara Perez pela primeira vez.

1. Abra o Microsoft Edge.

2. Na barra de endereços, insira **login.microsoft.com**.

3. Faça logon como **sara@WWLxZZZZZ.onmicrosoft.com**, (onde ZZZZZZ é seu ID de locatário exclusivo fornecido pelo seu provedor de hospedagem do laboratório).

4. Insira sua senha temporária **Naja8996**.

5. Agora você vai receber a notificação para atualizar sua senha. No campo Senha atual, digite **Naja8996**.

6. No campo Nova senha, insira **SC900-Lab**.  No campo Confirme sua senha, digite SC900-Lab e clique em entrar. Observação: a prática recomendada é usar uma senha mais segura. Essa senha foi escolhida por conveniência e apenas para os fins deste laboratório.

7. Agora você deve estar conectado ao Microsoft 365.

8. **Saia** de todas as guias do navegador clicando no ícone do usuário ao lado do endereço de email, no canto superior direito da tela. Em seguida, feche todas as janelas do navegador.



#### Revisão
Neste laboratório, você começou sua exploração inicial do Azure AD. Como os assinantes do Microsoft 365 estão usando o Azure AD automaticamente, você descobriu que pode acessar os recursos e serviços do Azure AD pelo Portal de administração do Microsoft 365 ou pelo Portal do Azure.  Seja qual for sua abordagem preferida, você chegará ao mesmo lugar.  Você também passou pelo processo de criação de um novo usuário, além das diferentes configurações que podem ser definidas, incluindo grupos aos quais o usuário pode ser atribuído, a disponibilidade de funções e a atribuição de licenças de usuário.


