---
lab:
    title: 'Explorar a Central de Segurança do Azure'
    module: 'Módulo 3 Lição 2: Descrever as funcionalidades das soluções de segurança da Microsoft: Descrever os recursos de gerenciamento de segurança do Azure'
---


# Laboratório: Explorar a Central de Segurança do Azure 

## Visão geral do laboratório
Neste laboratório, vamos explorar a Central de Segurança do Azure e aprender como a Classificação de Segurança do Azure pode ser usada para melhorar a postura de segurança da sua organização.

  

**Tempo estimado**: 10-15 minutos

#### Tarefa 1: Nesta tarefa, vamos fazer um breve tour pela Central de Segurança do Azure.
1.	Abra o Microsoft Edge. Na barra de endereços, insira **portal.azure.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela de acesso, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (sendo ZZZZZZ o único ID de locatário fornecido pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    
    1. Insira sua senha de administrador fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Ao receber um aviso do Microsoft Edge para permanecer conectado, selecione **Sim**.

1. No canto superior esquerdo da tela, perto de Microsoft Azure, selecione o ícone para mostrar o menu (as três linhas horizontais, também conhecidas como ícone de hambúrguer). Depois, selecione **Todos os Serviços**.  
1. Na caixa para filtrar serviços, insira **Central de Segurança** e, a partir dos resultados, selecione **Central de Segurança**.
1. Observe as informações disponíveis na página Visão geral da central de segurança.  
1. Pode aparecer uma caixa de informações azul no topo da página, indicando que você pode estar vendo informações limitadas.  Selecione **clique aqui**.
    1. Para garantir que seu locatário tenha uma visibilidade ampla, atribua as funções necessárias.  Selecione **Administrador de Segurança** e depois **Obter acesso** na parte inferior da página.
   
     1. É provável que apareça a mensagem O grupo de gerenciamento raiz não existe.  Pela descrição, o sistema vai criar um grupo para você.  Pode levar até 15 minutos para concluir (mas geralmente é mais rápido). Depois, você pode repetir o processo para obter acesso.  Ao obter acesso, selecione **Central de Segurança** no canto superior esquerdo da página, acima de Obter permissões, e atualize a página Visão geral da central de segurança.
1. As informações no topo da página incluem o número de assinaturas do Azure, o número de Recursos acessados, o número de recomendações ativas e os alertas de segurança.  No corpo central da página, os cartões mostram a Classificação de segurança, a Conformidade regulatória, Insights, o Azure Defender, entre outros.  
1. Na parte superior da página, selecione **Recursos avaliados**.  Você encontrará a página de inventário, que mostra sua assinatura do Azure Pass.  Selecione **Azure Pass – Sponsorship**.
1. A página Resource health apresenta uma lista de recomendações.  A partir dessa lista, selecione **Deve haver mais de um proprietário atribuído à sua assinatura**. 
1. Clique na seta para baixo, ao lado de Etapas de correção. Observe que etapas de correção detalhadas são apresentadas junto com a opção de executar ações.  
1. Selecione **Central de Segurança** no canto superior esquerdo da tela para voltar à página Visão geral da Central de Segurança.
1. Na parte superior da página, selecione **Recomendações ativas**.  
1. A página de recomendações mostra as ações específicas que podem ser realizadas para aumentar o potencial da classificação de segurança.  Saia da página de recomendações selecionando o **X** no canto superior direito da tela.
1. Na página principal, selecione **Conformidade regulatória**.
1. A página Conformidade regulatória apresenta uma lista de controles de conformidade.  Em cada controle, tem um conjunto de avaliações com base no Azure Security Benchmark, com recomendações para você proteger suas soluções de nuvem no Azure.
1. Selecione **IM. Gerenciamento de Identidades** e depois **IM.4 Use controles de autenticação fortes para todos os acessos do Azure Active Directory**.  A lista mostra ações de responsabilidade do cliente que podem ser realizadas para melhorar a conformidade.
1. Selecione o **X** no canto superior direito da tela para voltar à página Visão Geral da Central de Segurança. 
1. Deixe a página Visão geral da central de segurança aberta; vamos usá-la na próxima tarefa.


#### Tarefa 2: Nesta tarefa, vamos navegar pela Classificação de segurança do Azure e explorar recomendações que podem melhorar sua classificação de segurança. 

1. Na página Visão geral da central de segurança, selecione o cartão **Classificação de Segurança**.

2. Selecione **Azure Pass – Sponsorship**.  Observe a sua classificação de segurança.
3. Na página de recomendações, selecione **Gerenciar acesso e permissões**. Perceba que há um item vermelho nesse grupo.
4. Selecione o item **Deve haver mais de um proprietário atribuído à sua assinatura**, que mostra o status do resource health em vermelho. Se não der para selecionar esse item.
    1. No canto superior esquerdo da página, selecione **Central de Segurança**, acima de Recomendações.
    
    1. No painel de navegação esquerdo, selecione **Recomendações**.
    1. Na página de recomendações, selecione **Gerenciar acesso e permissões**. Perceba que há um item vermelho nesse grupo.
    1. Selecione o item **Deve haver mais de um proprietário atribuído à sua assinatura**, que mostra o status do resource health em vermelho. 
5. Selecione **Assinatura do Azure**.
6. No topo da página Controle de acesso (IAM), selecione **+Adicionar** e depois **Adicionar atribuição de função** no menu suspenso.
7. No campo Função, insira **Proprietário** e selecione **Proprietário** na lista de resultados.
8. Na lista de usuários, selecione **Alex Wilber** e depois **Salvar** na parte inferior da página.
9. Pode levar até 24 horas para atualizar o status. Depois, sua classificação de segurança também vai ser atualizada, já que todos os itens do grupo Gerenciar acesso e permissões serão atendidos.
10. No canto superior esquerdo da página, acima de Azure Pass, selecione **Central de Segurança** e depois **Visão Geral** para voltar à página da visão geral da central de segurança.
11. Deixe essa página aberta para a próxima tarefa.


#### Tarefa 3:  Lembre-se de que a Central de segurança é disponibilizada de dois modos: Azure Defender OFF (gratuito) e Azure Defender ON. Nesta tarefa, vamos ver como habilitar e desabilitar o Azure Defender.

1.	Na página Visão geral da central de segurança, selecione **Habilitar o Azure Defender** no cartão Azure Defender.

2.	Selecione a caixa **Azure Defender on**.  Observe como o status de todos os planos do defender mudam para On e observe também o preço de cada item. Depois, selecione **Salvar** no canto superior esquerdo da página.
3.	Volte à página Central de segurança selecionando **Central de Segurança** no canto superior esquerdo da página.   Pode levar alguns minutos para o cartão do Azure Defender refletir essa mudança.  Se necessário, atualize a página.
4.	Para desabilitar o Azure Defender, selecione **Preços e configurações**, à esquerda no painel de navegação da página da central de segurança, e depois **Assinatura Azure Pass – Sponsorship**.
5.	Na página Planos do Azure Defender, selecione a caixa **Azure Defender off** e depois **Salvar** no canto superior esquerdo da página.
6.	Uma janela pop-up vai aparecer solicitando a confirmação do downgrade.  Desmarque a caixa que indica para a Microsoft entrar em contato com você e selecione **Confirmar**.
7.	Agora pode fechar a guia do navegador para sair do portal do Azure.


#### Revisão
Neste laboratório, exploramos a Central de Segurança do Azure e aprendemos como a Classificação de Segurança do Azure pode ser usada para melhorar a postura de segurança da nossa organização.
