---
lab:
    title: 'Explorar o Azure Sentinel'
    module: 'Módulo 3 Lição 3: Descrever as funcionalidades das soluções de segurança da Microsoft: Descrever os recursos de segurança do Azure Sentinel'
---


# Laboratório: Explorar o Azure Sentinel 

## Visão geral do laboratório
Neste laboratório, vamos acompanhar o processo de criação de uma instância do Azure Sentinel.  Além disso, também vamos configurar as permissões para garantir o acesso aos recursos que vão ser implantados para comportar o Azure Sentinel.  Depois de concluir essa configuração básica, vamos poder acompanhar as etapas de conexão do Sentinel às fontes de dados, usar análises internas para notificar suspeitas e, por fim, vamos explorar a capacidade de automação.  

  

**Tempo estimado**: 30-45 minutos

#### Tarefa 1:  Criar uma instância do Azure Sentinel.

1. Abra o Microsoft Edge. Na barra de endereços, insira **portal.azure.com**.

2. Entre com suas credenciais de administrador.
    1. Na janela de acesso, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (sendo ZZZZZZ o único ID de locatário fornecido pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    
    1. Insira sua senha de administrador fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Ao receber um aviso do Microsoft Edge para permanecer conectado, selecione **Sim**.

3. No canto superior esquerdo da tela, perto de Microsoft Azure, selecione o ícone para mostrar o menu (as três linhas horizontais, também conhecidas como ícone de hambúrguer). Depois, selecione **Todos os Serviços**.  

4. Na caixa para filtrar serviços, insira **Sentinel** e selecione **Azure Sentinel** na lista.

5. Na página Azure Sentinel, selecione **Criar Azure Sentinel**.

6. Na página Adicionar o Azure Sentinel a um espaço de trabalho, selecione **Criar novo espaço de trabalho**.

7. Na guia Básico da página Criar espaço de trabalho do Log Analytics, insira:
    1. Assinatura:  **Azure Pass – Sponsorship**
   
    1. Grupo de recursos: selecione **Criar Novo**, insira o nome **SC900-ResourceGroup** e selecione **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Região: **Leste dos EUA** (manter padrão)
    1. Selecione **Avançar: Tipo de preço >**

8. Para o Tipo de Preço, mantenha as configurações padrão: **Pay-as-you-go (per GB 2018)**. Depois, selecione **Next: Marcas >**.

9. Pode deixar Marcas em branco. Depois, selecione **Revisar + Criar**.

10. Verifique as informações inseridas e selecione **Criar**.

11. Se você não encontrar o espaço de trabalho na lista, selecione **Atualizar** e selecione **Adicionar**.

12. Uma vez que o espaço de trabalho estiver adicionado, a página Notícias e Guias do Azure Sentinel |  será exibida.  Observe as três etapas listadas na página de Introdução.

13. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### Tarefa 2:  Com a instância criada do Azure Sentinel, precisamos verificar se você tem o acesso necessário aos recursos implantados para comportar o Azure Sentinel.  Nesta tarefa, vamos abrir a página de controle de acesso (IAM) do grupo de recursos criado com a instância do Azure Sentinel, visualizar as funções disponíveis e atribuir a você a função necessária (administrador MOD). Atribuir a função a nível do grupo de recursos vai garantir que ela seja aplicada a todos os recursos implantados para comportar o Azure Sentinel.

1. No canto superior esquerdo da página Azure Sentinel, em cima de Azure Sentinel, selecione **Todos os Serviços**.

2. Na caixa para filtrar serviços, insira grupos de recursos e selecione **Grupos de recursos** na lista gerada.

3. Na página Grupos de recursos, selecione o grupo de recursos que você criou com o Azure Sentinel, **SC900-ResourceGroup**.

4. Na página SC900-ResourceGroup, selecione **Controle de acesso (IAM)**, à esquerda no painel de navegação.

5. Na página Controle de acesso, selecione **Exibir meu acesso**.  Observe que a função atual é Administrador de segurança.  Feche a janela de atribuições do Administrador MOD selecionando o **X** no canto superior direito da tela.

6. Na página Controle de acesso, selecione **+Adicionar** e depois **Adicionar atribuição de função**.

7. A janela Adicionar atribuição de função vai ser aberta.  Selecione a seta para baixo no campo Selecionar função para exibir as funções disponíveis.  Para este laboratório, selecione **Proprietário**.  OBSERVAÇÃO:  Como prática recomendada, você deve atribuir o privilégio mínimo exigido para a função.  Verifique as permissões no Azure Sentinel para referência.  https://docs.microsoft.com/br-br/azure/sentinel/roles

8. Na lista de usuários exibida, selecione **Administrador MOD**.

9. Selecione **Salvar** na parte inferior da página.

10. Na página de controle de acesso, selecione **Exibir meu acesso** para confirmar a função adicionada. Depois, feche a janela selecionando o **X** no canto superior direito.

11. Volte à página Todos os serviços selecionando **Todos os Serviços** no canto superior esquerdo da página, em cima de Grupos de recursos.

#### Tarefa 3:  Nesta tarefa, vamos acompanhar o processo de conexão do Azure Sentinel à sua fonte de dados para começar a coletar dados. Observação: pode levar algum tempo para o conector ter o status alterado para conectado (~30 minutos dependendo do locatário).

1. Na caixa Filtrar serviços da página Todos os serviços, insira **Azure Sentinel** e selecione **Azure Sentinel** na lista de resultados. 

2. Na página Azure Sentinel, selecione o espaço de trabalho criado com a instância do Azure Sentinel, **SC900-LogAnalytics-workspace**.

3. A primeira etapa com o Azure Sentinel é conseguir coletar dados. À esquerda no painel de navegação, selecione **Conectores de dados**, listado em configuração.

4. Na página Conectores de dados, role para baixo na janela principal para exibir a extensa lista de conectores disponíveis. Na caixa Pesquisar da página dos conectores de dados, insira **Azure** e selecione **Azure Active Directory** na lista de resultados.

5. A janela do conector do Azure Active Directory será aberta.  Selecione **Abrir página do conector**.

6. Na página Conector do Azure Active Directory, verifique a descrição e observe o conteúdo relacionado, incluindo pastas de trabalho, consultas e modelos de regras analíticas.  

7. A guia de instruções, na janela principal, apresenta os pré-requisitos para integrar o Azure Sentinel ao Azure Active Directory.   Em configuração, selecione **Logs de entrada** e depois Aplicar Mudanças (é possível escolher múltiplos conectores).

8. Na guia Próximas etapas, observe a lista de pastas de trabalho recomendadas.   Nas pastas de trabalho recomendadas, selecione **Logs de entrada do Azure** (é possível escolher pastas de trabalho adicionais).

9. Na página de pastas de trabalho e com a guia de modelos selecionada (sublinhada), selecione **Logs de entrada do Azure**. 

10. Na janela Logs de entrada do Azure aberta, verifique a descrição e selecione **Exibir modelo**.  Saia do modelo selecionando o **X** no canto superior direito da tela.  Selecione **Salvar** na parte inferior da página e depois **OK** para salvar a pasta de trabalho na localização padrão.

11. No canto superior esquerdo da página Pastas de trabalho, acima de Pastas de Trabalho, selecione **Azure Sentinel**. Você vai voltar à página Conectores de Dados do Azure Sentinel.

12. O topo da página Conectores de dados deve exibir 1 conexão, indicando que agora você se conectou ao Azure Active Directory.

13. À esquerda no painel de navegação, selecione **Pastas de trabalho**.

14. Na página Pastas de trabalho, selecione a guia **Minhas pastas de trabalho**, que fica acima da caixa de pesquisa.  A pasta de trabalho que você acaba de salvar está listada e disponível para você exibir e monitorar seus dados.

15. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### Tarefa 4:  Nesta tarefa, vamos acompanhar o uso de um modelo interno de regra de análise para criar uma regra de notificação sobre atividades suspeitas.

1. À esquerda no painel de navegação, selecione **Análise**.

2. A página Análise mostra regras ativas (a Detecção avançada de ataques multiestágio está habilitada por padrão) e permite acessar os modelos de Regras.  Selecione a guia **Modelos de regras**.  Observe a lista de modelos disponíveis e as diferentes formas de filtrar essa lista.  Com os alertas internos de análise no espaço de trabalho do Azure Sentinel, você recebe uma notificação quando algo suspeito acontece.

3. Na barra de pesquisa, insira **Portal do Azure**.  Selecione **Falha de logon no Portal do Azure**.  

4. Na janela que abrir, leia a descrição e as informações associadas ao modelo.  Selecione **Criar regra** na parte inferior da página.

5. No Assistente de regra de análise, revise as informações e selecione **Avançar: Definir lógica de regra >**.

6. A página Definir lógica de regra é onde você define a lógica da nova regra de análise. O modelo já apresenta algumas lógicas e configurações predefinidas.  Role a página para verificar as configurações disponíveis.  Mantenha as configurações padrão. Selecione **Avançar: Configurações de incidentes (prévia)>**.

7. Com as Configurações de incidentes, é possível agrupar os alertas do Azure Sentinel em um único Incidente a ser analisado. Você pode definir se os alertas disparados por essa regra de análise devem gerar incidentes.  Mantenha o padrão e selecione **Avançar: Resposta automatizada >**.

8. Na guia Resposta automatizada, observe que é possível adicionar um guia estratégico para automatizar a resposta.  Do mesmo modo, também é possível criar uma regra de automatização de incidente.  Selecione **+Adicionar** novo em automação de incidente.  Uma janela vai ser aberta para criar a nova regra de automação.  Toda regra de automação criada nesta página é disparada pela regra de análise que você está criando. Observe que é possível adicionar condições e definir ações para a regra.   Selecione **Cancelar** para sair dessa janela.

9. Selecione **Avançar: Revisão>** para revisar todos os detalhes relacionados à regra com base no modelo escolhido. Aqui, é possível escolher se você quer criar a rega, selecionando **Criar**, ou sair sem criar a regra, selecionando **X** no canto superior direito da página.

10. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### Tarefa 5:  Na tarefa anterior, nós criamos uma regra de análise para sermos alertados de atividades suspeitas.  O assistente também permite automatizar a resposta a um incidente com base nessa regra específica.  Você também pode criar regras de automação diretamente na opção de configuração de automação.

1. À esquerda no painel de navegação, selecione **Automação**.  

2. Selecione **+ Criar**. No menu suspenso, observe que é possível adicionar tanto um novo guia estratégico quanto uma nova regra.  Selecione **Adicionar nova regra**.  

3. Uma janela vai ser aberta para criar a nova regra de automação.  Observe que é possível adicionar condições e definir ações para a regra.  A única diferença é que a primeira condição é associar as regras de análise a que você quer aplicar essa regra de automação.  Ela aparecia acinzentada na tarefa anterior porque a automação estava sendo configurada para a regra específica.  Selecione **Cancelar** para sair da janela Criar nova regra de automação.

4. Deixe essa página aberta; vamos usá-la na próxima tarefa.


#### Tarefa 6:  Excluir o Grupo de recursos do Azure Sentinel.  O Azure Sentinel é cobrado de acordo com o volume da ingestão de dados para análise. Embora a quantidade de dados ingeridos durante este laboratório seja mínima, recomendamos que o grupo de recursos do Azure Sentinel seja excluído quando você terminar de explorar suas funcionalidades.

1. No canto superior esquerdo da página Azure Sentinel, em cima de Azure Sentinel, selecione **Todos os Serviços**.

2. Na caixa para filtrar serviços, insira grupos de recursos e selecione **Grupos de recursos** na lista gerada.

3. Na página Grupos de recursos, selecione o grupo de recursos que você criou com o Azure Sentinel, **SC900-ResourceGroup**.

4. Na parte superior central da página, selecione **Excluir grupo de recursos**.  Verifique o aviso de segurança.  Insira o nome do grupo de recursos, **SC900-ResourceGroup**, e selecione **Excluir** na parte inferior da página.  Vai levar alguns minutos para excluir o grupo de recursos.

5. Após verificar que o grupo de recursos foi excluído, feche a página do navegador. 


#### Revisão

Neste laboratório, acompanhamos o processo de criação de uma instância do Azure Sentinel.  Além disso, também configuramos as permissões para garantir o acesso aos recursos associados a essa instância do Azure Sentinel.  Por meio da nova instância do Azure Sentinel, pudemos acompanhar as etapas de conexão do Sentinel às fontes de dados, usar regras de análise internas para notificar suspeitas e explorar a capacidade de automação. Por fim, concluímos o laboratório excluindo o grupo de recursos associado à instância do Azure Sentinel que criamos.
