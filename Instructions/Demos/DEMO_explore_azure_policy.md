---
Demo:
    title: 'Azure Policy'
    module: 'Módulo 4 – Lição 5: Descrever os recursos das soluções de conformidade da Microsoft: Descrever o Azure Policy'
---


# Demonstração: Azure Policy

### Cenário da demonstração
Nesta demonstração, você verá o processo de configuração de uma política do Azure e o impacto dela.

#### Demonstração – Parte 1: Criar uma política para exigir uma marcação em um grupo de recursos (mostra as etapas para criar uma política de um modelo)

1. Abra o Microsoft Edge. Na barra de endereços, insira **portal.microsoft.com**.  Você já deve estar conectado, caso contrário, entre com suas credenciais de administrador.

1. Na caixa de pesquisa, na barra azul, na parte superior da página, ao lado de onde está escrito Microsoft Azure, insira **política** e selecione **Política** nos resultados da pesquisa.

1. Agora você está na visão geral da página Política. Observe as informações disponíveis no painel.

1. No painel de navegação esquerdo, em Criação, selecione **Atribuições**.  Você notará que já existe uma atribuição de política. Selecione **ASC Padrão**.  Observe o campo de descrição. Este é o conjunto padrão de políticas monitoradas pela Central de Segurança do Azure. Ele foi atribuído automaticamente como parte da integração à Central de Segurança. A atribuição padrão contém apenas políticas de auditoria. Para obter mais informações visite https://aka.ms/ascpolicies.  Retorne à página Atribuições de política selecionando o **X** no canto superior direito da página.

1. Na parte superior da página, selecione **Atribuir política**.

1. O assistente Atribuir política é aberto para orientar o administrador no processo de atribuição de uma política.  Ao lado do campo Definição de política, selecione as **reticências**.  É fornecida uma lista das definições de política disponíveis.  

1. Na barra de pesquisa, insira **Marcação**.

1. Nos resultados da pesquisa, selecione **Exigir uma marcação no grupo de recursos** (pode ser necessário rolar para baixo) e pressione **Selecionar**.  Observação: o efeito dessa política é negar a criação de qualquer novo grupo de recursos que não satisfaça o requisito.  

1. Observe o nome da atribuição padrão.  Mantenha o nome como está e, na parte inferior da página, selecione **Avançar**.

1. No campo Nome da marcação, insira **Ambiente** (os grupos de recursos exigirão uma Marcação de ambiente) e selecione **Avançar**.  

1. Na guia Correção, leia a descrição, mas não altere as configurações. Selecione **Próximo**

1. Na mensagem de não conformidade, insira **Uma marcação de ambiente é necessária** e selecione **Avançar**. Observação: essa mensagem aparecerá como o motivo da não conformidade para grupos de recursos que foram criados antes da atribuição da política e não têm uma Marcação de ambiente.  Para grupos de recursos criados depois que a política foi criada, a criação do grupo de recursos será negada se não houver nenhuma marcação de ambiente.

1. Revise a atribuição de política e selecione Criar.  Se você não vir a política imediatamente, selecione **Atualizar**. Observação: Pode levar até 30 minutos para que a política entre em vigor.

1. Saia da página Atribuições de política selecionando o **X** no canto superior direito da tela.

1. Agora você está na página dos serviços do Azure.  Mantenha esta página aberta, você precisará dela para a próxima tarefa.

#### Demonstração – Parte 2:  Mostrar o impacto da política criando um grupo de recursos sem uma marcação e, a seguir, corrigir a política para ter uma marcação.

1. Na parte superior da página, em Serviços do Azure, selecione **Grupos de recursos**. Se você não vir a opção listada, insira Grupos de recursos na barra de pesquisa e o selecione de lá.

1. No canto superior esquerdo da página, selecione **+ Criar**.

1. Na guia Básico de Criar um grupo de recursos, deixe o campo Assinatura como está, Azure Pass – Sponsorship.

1. No campo Grupo de recursos, insira **SC900-Labs**.

1. Deixe a configuração de Região como padrão e selecione **Avançar**:** Marcações**.

1. Deixe os campos Nome e Valor da marcação em branco.  NÃO PREENCHA e selecione **Revisar + criar**.

1. Você verá uma validação aprovada (o nome e o valor da marcação não são campos obrigatórios no assistente). Selecione **Criar**.

1. Você verá uma mensagem de falha na parte superior da tela: “Falha ao criar o grupo de recursos. Veja os detalhes do erro”.  Selecione **Exibir detalhes do erro**. A condição que faz parte da política do Azure não foi atendida, portanto, a criação do grupo de recursos foi bloqueada por não conformidade. Observação: Se você não vir a mensagem de falha e o grupo de recursos for criado, é porque a política ainda não entrou em vigor.  Vá para a página Política da política criada na tarefa anterior e, quando a política entrar em vigor, você verá que o recurso não é compatível.  A página de detalhes incluirá a mensagem de não conformidade.

1. O resumo do erro mostra o tipo de erro: “O recurso ‘SC900-Labs’ não foi permitido pela política”.  Feche a janela selecionando o **X** no canto superior esquerdo da tela.


1. Na janela Criar um grupo de recursos, selecione **<Anterior**.

1. Você está de volta à página Marcações para Criar um grupo de recursos.  No campo Nome, insira Ambiente e no campo Valor, insira **SC900-Labs** e selecione **Avançar: Revisar + Criar >**.

1. Verifique a marcação e selecione **Criar**.

1. Você verá o grupo de recursos listado.  Como a marcação foi fornecida no grupo de recursos, a condição incluída como parte da política do Azure foi atendida.  O grupo de recursos está em conformidade com a política.

#### Revisão

Nesta demonstração, você mostrou o processo de configuração de uma política do Azure e o impacto dela.
