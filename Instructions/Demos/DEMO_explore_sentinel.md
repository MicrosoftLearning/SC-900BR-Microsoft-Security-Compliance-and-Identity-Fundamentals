---
Demo:
    title: 'Azure Sentinel'
    module: 'Módulo 3 Lição 3: Descrever as funcionalidades das soluções de segurança da Microsoft: Descrever os recursos de segurança do Azure Sentinel'
---


# Demonstração: Azure Sentinel 

### Cenário da demonstração
Nesta demonstração, você passará pelo processo de criação de uma instância do Azure Sentinel.  Você também vai configurar as permissões para garantir o acesso aos recursos que serão implantados para dar suporte ao Azure Sentinel.  Depois dessa configuração básica, você verá as etapas necessárias para conectar o Sentinel às suas fontes de dados e usar funções analíticas integradas para receber notificações sobre suspeitas. Por último, você vai explorar os recursos de automação.  

#### Parte 1 da demonstração:  Criar uma instância do Azure Sentinel

1. Abra a guia do navegador **Home-Microsoft Azure**.  Se você tiver fechado a guia anteriormente, abra uma página do navegador e, na barra de endereços, digite portal.azure.com e conecte-se de volta.

1. Na caixa de pesquisa, na barra azul que fica na parte superior da página, perto de onde está escrito Microsoft Azure, digite **sentinel** e selecione **Azure Sentinel** nos resultados da pesquisa.

1. Na página do Azure Sentinel, selecione **Criar Azure Sentinel**.

1. Na página Adicionar o Azure Sentinel a um workspace, selecione **Criar um novo workspace**.

1. Na guia básica Criar workspace do Log Analytics, insira o seguinte:
    1. Assinatura:  **Azure Pass – Sponsorship**
    1. Grupo de recursos: selecione **Criar novo**, insira o nome **SC900-Sentinel-RG** e clique em **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Região: **Leste dos EUA** (deixar padrão)
    1. Selecione **Avançar: Tipo de preço >**

1. Para o tipo de preço, deixe as configurações padrão: **Pagamento conforme o uso (por GB 2018)**. Depois, selecione **Avançar: Tags >**.

1. Para as tags, você pode deixar a opção em branco e selecionar **Revisar + Criar**.

1. Verifique as informações inseridas e clique em **Criar**.

1. Pode levar um ou dois minutos até que o novo workspace seja listado, caso você ainda não consiga vê-lo, clique em **Atualizar** e selecione **Adicionar**.

1. Assim que o novo workspace for adicionado, a página Novidades | e Guias do Azure Sentinel será exibida.  Veja as três etapas listadas na página de Introdução.

1. Mantenha esta página aberta, pois ela será usada na próxima tarefa.

#### Parte 2 da demonstração:  Com a instância do Azure Sentinel criada, talvez seja prudente verificar se você tem o acesso necessário aos recursos que são implantados para dar suporte ao Azure Sentinel.  Nesta tarefa, você vai entrar na página de controle de acesso (IAM) do grupo de recursos criado com a instância do Azure Sentinel, verificar os papéis disponíveis e atribuir a você a função necessária (administrador de MOD). A atribuição do papel no nível do grupo de recursos garante que ele será aplicado a todos os recursos implantados para dar suporte ao Azure Sentinel.

1. Na caixa de pesquisa, na barra azul que fica na parte superior da página, perto de onde está escrito Microsoft Azure, digite **grupos de recursos** e selecione **Grupos de recursos** nos resultados da pesquisa.

1. Na página de Grupos de recursos, selecione o grupo de recursos que você criou com o Azure Sentinel, **SC900-Sentinel-RG**.

1. Na página do SC900-Sentinel-RG, selecione **Controle de acesso (IAM)** no painel de navegação à esquerda.

1. Na página de Controle de acesso, selecione **Exibir meu acesso**.  Veja que a função atual é de Administrador de serviços.  Feche a janela de atribuições de Administrador de MOD clicando no **X** do canto superior direito da janela.

1. Na página de Controle de acesso, selecione **+ Adicionar** e, em seguida, **Adicionar atribuição de função**.

1. A janela Adicionar atribuição de função é aberta.  Clique na seta suspensa do campo Selecionar uma função para exibir as funções disponíveis. Na caixa de pesquisa de seleção de função, digite **sentinel** para ver as quatro funções associadas ao Sentinel. Uma prática recomendada é atribuir o menor privilégio necessário para a função.  Para os fins deste laboratório, digite **Proprietário** na caixa de pesquisa e selecione **Proprietário** nos resultados.  Como referência, revise as Permissões no Azure Sentinel:  https://docs.microsoft.com/pt-br/azure/sentinel/roles

1. Da lista de usuários exibida, selecione **Administrador de MOD**.

1. Clique em **Salvar** na parte inferior da página.

1. Na página de Controle de acesso, selecione **Exibir meu acesso.** Para confirmar que a função foi adicionada. Em seguida, feche a janela clicando no **X** no canto superior direito.

#### Parte 3 da demonstração:  Nesta parte da demonstração, você verá como é o processo para conectar o Azure Sentinel com a sua fonte de dados para começar a coletar dados.  Observação: pode levar um tempo até que o status de um conector seja exibido como conectado (aproximadamente 30 minutos, dependendo do locatário).

1. Na caixa de pesquisa, na barra azul que fica na parte superior da página, perto de onde está escrito Microsoft Azure, digite **sentinel** e selecione **Azure Sentinel** nos resultados da pesquisa.

1. Na página do Azure Sentinel, selecione o workspace que você criou com a instância do Azure Sentinel, **SC900-LogAnalytics-workspace**.

1. A primeira etapa com o Azure Sentinel é conseguir coletar dados. No painel de navegação à esquerda, selecione **Conectores de dados**, listados abaixo das configurações.

1. Na página de Conectores de dados, role a janela principal para baixo para ver a lista extensa de conectores disponíveis. Na caixa de pesquisa da página de conectores de dados, digite **Azure**. Em seguida, selecione **Azure Active Directory** na lista.

1. A janela do conector do Azure Active Directory é aberta.  Clique em **Abrir página do conector**.

1. Na página do conector do Azure Active Directory, revise a descrição e veja o conteúdo relacionado, que inclui pastas de trabalho, consultas e modelos de regras analíticas.  

1. A guia de instruções da janela principal traz os pré-requisitos para integrar o Azure Sentinel ao Azure Active Directory.   Em Configurações, selecione **Logs de entrada** e depois Aplicar alterações (vários conectores podem ser escolhidos).  Observação: pode levar um tempo até que o status do conector seja exibido como conectado (aproximadamente 30 minutos ou mais).  Como referência:
    1. reveja as Permissões no Azure Sentinel:  https://docs.microsoft.com/pt-br/azure/sentinel/roles
    1. Conectar o Azure Active Directory:  https://docs.microsoft.com/pt-br/azure/sentinel/connect-azure-active-directory

1. Na guia Próximas etapas, veja a lista de pastas de trabalho recomendadas.   Na seção Pastas de trabalho recomendadas, selecione **Logs de entrada do Azure** (outras pastas de trabalho podem ser selecionadas).

1. Na página de pastas de trabalho e com a guia “Modelos” selecionada (sublinhada), selecione **Logs de entrada do Azure**.

1. Na janela de logs de entrada do Azure AD que será aberta, revise a descrição e selecione **Exibir modelo**.  Saia do modelo clicando no **X** do canto superior direito da tela.  Selecione **Salvar** na parte inferior da página e clique em **OK** para salvar a pasta de trabalho no local padrão.

1. No canto superior esquerdo da página Pastas de trabalho, acima de onde está escrito pastas de trabalho, clique em **Azure Sentinel**. Você voltará para a página de Conectores de dados do Azure Sentinel.

1. A parte superior dessa página deve mostrar a mensagem “1 conectado”, informando que você agora está conectado ao Azure Active Directory.

1. No painel de navegação à esquerda, selecione **Pastas de trabalho**.

1. Na página Pastas de trabalho, selecione a guia **Minhas pastas de trabalho**, que fica acima da caixa de pesquisa.  A pasta de trabalho que você acabou de salvar está na lista e disponível para que você visualize e monitore os dados.  Os próximos logins serão refletidos na pasta de trabalho, você pode escolher mostrar essas informações.

1. Mantenha esta página aberta, pois ela será usada na próxima tarefa.

#### Parte 4 da demonstração (opcional):  Nesta parte da demonstração, você verá como é o processo para usar um modelo de regra analítica integrado para criar uma regra e ser notificado quando ocorrer algo suspeito.

1. No painel de navegação à esquerda, selecione **Análises**.

1. A página de Análises mostrará regras ativas (a detecção avançada de ataques em vários estágios é ativada por padrão), além de dar acesso aos modelos de regras.  Selecione a guia **Modelos de regras**.  Veja a lista de modelos disponíveis e as diferentes formas de filtrá-la.  Com os alertas internos de análise no espaço de trabalho do Azure Sentinel, você será notificado quando algo suspeito ocorrer.

1. Na barra de pesquisa, digite **Portal do Azure**.  Selecione **Tentativas de logon no Portal do Azure com falha**.  

1. Na janela que será aberta, leia a descrição e revise as informações associadas ao modelo.  Selecione **Criar regra** na parte inferior da página.
    1. No Assistente de regra analítica, revise as informações e clique em **Avançar: Definir lógica da regra >**.
    1. A página Definir a lógica da regra é onde você define a lógica da sua nova regra analítica. O modelo já traz parte da lógica e algumas configurações predefinidas.  Role a página para ver as configurações disponíveis.  Mantenha os as configurações padrão. Selecione **Avançar: Configurações de incidentes (versão prévia) >**.
    1. Com as Configurações de incidentes, os alertas do Azure Sentinel podem ser agrupados em um único incidente que deve ser examinado. É possível definir se os alertas acionados por essa regra analítica devem gerar incidentes.  Mantenha as configurações padrão e clique em **Avançar: Resposta automatizada >**.
    1. Na guia Resposta automatizada, observe que é possível adicionar um guia estratégico para automatizar a resposta.  Do mesmo modo, também é possível criar uma regra de automatização de incidente.  Selecione **+Adicionar** novo em automação de incidente.  Uma janela vai ser aberta para criar a nova regra de automação.  Qualquer regra de automação criada nesta página é disparada pela regra analítica selecionada originalmente, que neste caso é Falha de logon no Portal do Azure.  Observe que é possível adicionar condições e definir ações para a regra.   Selecione **Cancelar** para sair dessa janela.
    1. Selecione **Avançar: Revisão >** para revisar todos os detalhes associados à regra e baseados no modelo escolhido. Neste momento, você pode optar por criar a regra, selecionando **Criar**, ou sair sem criá-la, clicando no **X** no canto superior direito da página.

1. Mantenha esta página aberta, pois ela será usada na próxima tarefa.

#### Parte 5 da demonstração (opcional):  Na etapa anterior, você criou uma regra analítica para ser alertado a respeito de atividades suspeitas.  O assistente traz a opção integrada de automatizar a resposta a um incidente com base na regra específica.  No entanto, você também pode criar regras de automação acessando diretamente a opção de configuração de automação.

1. No painel de navegação à esquerda, selecione **Automação**.  

1. Selecione **+ Criar**. No menu suspenso, veja como é possível escolher entre adicionar um novo guia estratégico ou adicionar uma nova regra.  Selecione **Adicionar nova regra**.  
    1. Uma janela para criar uma nova regra de automação é aberta.  Observe que você pode adicionar condições e definir ações para a regra.  A única distinção é que a primeira condição é associar a regra analítica (ou regras) às quais você quer aplicar essa regra de automação.  Essa opção estava acinzentada na tarefa anterior porque a automação estava sendo configurada para a regra específica.  Clique em **Cancelar** para sair da janela Criar nova regra de automação.

1. Mantenha esta página aberta, pois ela será usada na próxima tarefa.

#### Etapa 6: DESATIVAÇÃO – Instrutor realiza esta etapa após a aula. Exclua o Grupo de recursos do Azure Sentinel.  O Azure Sentinel é cobrado com base no volume de dados ingeridos para análise. Embora a quantidade de dados ingerida neste laboratório seja mínima, é recomendável que você exclua o grupo de recursos do Azure Sentinel quando terminar de explorar os recursos e funcionalidades do Azure Sentinel.

1. Na página do Azure Sentinel, no canto superior esquerdo, abaixo de onde está escrito Azure Sentinel, clique em **Todos os serviços**.

1. Na caixa para filtrar serviços, digite grupos de recursos. Em seguida, na lista fornecida, clique em **Grupos de recursos**.

1. Na página de Grupos de recursos, selecione o grupo de recursos que você criou com o Azure Sentinel, **SC900-Sentinel-RG**.

1. No centro da parte superior da página, clique em **Excluir grupo de recursos**.  Examine o aviso.  Insira o nome do grupo de recursos, **SC900-Sentinel-RG**, e clique em **Excluir** na parte inferior da página.  A exclusão do grupo de recursos levará alguns minutos.

1. Depois de verificar que o grupo de recursos foi excluído, feche a página do navegador. 

#### Revisão

Nesta demonstração, você mostrou o processo de criação de uma instância do Azure Sentinel.  Você também mostrou como configurar as permissões para garantir o acesso aos recursos associados à sua instância do Azure Sentinel.  Com a instância do Azure Sentinel criada, você percorreu as etapas necessárias para conectar o Sentinel a fontes de dados, descobriu como usar regras analíticas integradas para receber notificações sobre suspeitas e, por último, explorou os recursos de automação. Você concluiu a demonstração excluindo o grupo de recursos associado à instância do Azure Sentinel que criou.