---
Demo:
    title: 'Microsoft Cloud App Security'
    module: 'Módulo 3 – Lição 4: Descrever os recursos das soluções de segurança da Microsoft: Descrever a proteção contra ameaças com o Microsoft 365 Defender'
---


# Demonstração: Microsoft Cloud App Security

### Cenário da demonstração
Nesta demonstração, você mostrará os recursos do Microsoft Cloud App Security.  Você apresentará ao aluno as informações disponíveis no painel do Cloud Discovery, além dos recursos disponíveis para investigar as descobertas e controlar o impacto na sua organização por meio de políticas.  Observação:  A organização deve ter uma licença para usar o Microsoft Cloud App Security, que é um serviço de assinatura baseado no usuário.  

#### Demonstração – Parte 1: Explorar o Cloud Discovery.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.  Você já deve estar conectado como administrador.  Se não estiver, entre com suas credenciais de administrador.

1. No painel de navegação esquerdo do centro de administração do Microsoft 365, selecione **Mostrar tudo**.  Explique com clareza que os vários centros de administração do Microsoft 365 possam ser acessados aqui.

1. Em Centros de administração, selecione **Segurança**.  Uma nova página do navegador é aberta na página de boas-vindas do portal do Microsoft 365 Defender.  

1. Se for a primeira vez que você visita o portal do Microsoft 365 Defender, talvez você veja uma janela pop-up que exibe uma apresentação rápida.  Feche a janela.

1. Na parte inferior do painel de navegação esquerdo da página do Microsoft 365 Defender, selecione **Mais recursos**.

1. No cartão do **Microsoft Cloud App Security**, selecione **Abrir**.  Uma nova página do navegador é aberta no painel do Cloud App Security.  Observe os cartões de informações disponíveis.  É possível que você não veja nenhuma informação nos cartões, uma vez que este é um ambiente de locatário de laboratório pré-configurado que não foi usado com frequência.  

1. No painel de navegação esquerdo, selecione **Descobrir** e, no menu suspenso, selecione o **painel do Cloud Discovery**.  O painel inclui uma visão geral dos aplicativos descobertos, categorias de aplicativos, níveis de risco e muito mais.  

    1. Na parte superior da página do Cloud Discovery, selecione a guia **Aplicativos descobertos**.  A janela de aplicativos descobertos fornece uma exibição mais detalhada dos aplicativos descobertos, incluindo pontuação de risco, tráfego, número de usuários e muito mais.

        1. De qualquer item da lista, selecione as **reticências** na coluna de ações da tabela.  Observe as várias opções disponíveis, incluindo a capacidade de marcar um aplicativo como sancionado ou não sancionado.  Selecione as reticências, de novo, para fechar a caixa de ações.

        1. Se você selecionar um item de linha específico, uma página de detalhes para o aplicativo específico será aberta.  Selecione um item da lista.  No item selecionado, passe por cada guia na parte superior da página de detalhes:  **Uso**, **Informações, IP**, **Endereços**, **Usuários** e **Alertas**. Quando terminar de explorar a página de detalhes, volte aos aplicativos descobertos, selecionando **Aplicativos descobertos** no painel de navegação esquerdo.

    1. Na parte superior da página, selecione a guia **Endereços IP** (equivale a selecionar Endereços IP no painel de navegação esquerdo).  Aqui você encontrará dados incluindo o número de transações, quantidade de tráfego e valores de upload, por endereços IP.  Observe que você também pode filtrar por endereço IP específico ou exportar os dados para análise posterior.

    1. Na parte superior da página (ou no painel de navegação esquerdo), selecione **Usuários**.  Esse é o mesmo tipo de informação fornecida ao selecionar endereços IP, mas, dessa vez, é listado para usuários individuais.  Aqui, novamente, você filtra por usuário específico e exporta dados para análise posterior.

1. As informações fornecidas nessas guias são baseadas em relatórios de instantâneos de logs de tráfego que você carrega manualmente de seus firewalls e proxies ou de relatórios contínuos que analisam todos os logs que são encaminhados de sua rede usando o Cloud App Security.  Para ver onde isso está configurado, selecione as **reticências** no canto superior direito da página.

    1. Selecione a primeira opção, **Criar relatório de instantâneos do Cloud Discovery**. Aqui, você preenche os detalhes solicitados e carrega os logs de tráfego para gerar e carregar um relatório.  Selecione **Cancelar**.  Os dados que você vê no seu locatário de laboratório vieram de um relatório de instantâneos. Você pode ver essas informações no canto superior direito da tela.

    1. Para ver a opção de relatórios contínuos, selecione as **reticências** no canto superior direito da página e, no menu suspenso, selecione **Configurar upload automático**.  Não há fontes de dados conectadas, mas é aqui que você adiciona uma fonte de dados. Selecione a seta suspensa **Selecionar dispositivo** para ver os tipos de dispositivos que você pode conectar como fonte de dados.  Selecione **Cancelar** para sair.

1. Outro ponto a ser destacado é que você pode se conectar aos aplicativos diretamente, configurando conectores de aplicativos que fornecerão maior visibilidade e controle sobre seus aplicativos de nuvem. No canto superior esquerdo da tela, selecione o **ícone de engrenagem Configurações** e, na lista suspensa, selecione **Conectores de aplicativos**.  

    1. Na página de aplicativos Conectados, você deve ver o Office 365 na lista com o status de conectado.  Se o Office 365 estiver mostrando um erro de conexão, provavelmente é porque a Auditoria não está ativada.

    1. Selecione **+Conectar um aplicativo** e, na lista suspensa, selecione **Microsoft Azure**.  Na janela pop-up do Microsoft Azure, selecione **Conectar ao Microsoft Azure**.  Você verá um status conectado e informações sobre a verificação de usuários, dados e atividades.  Selecione o **botão Fechar**.

1. Deixe essa página aberta para ser usada na próxima tarefa.

#### Demonstração – Parte 2: Explorar maneiras de investigar as atividades registradas.

1. No painel de navegação esquerdo, em **Investigar**, selecione **Log de atividades**.  Aqui você obtém visibilidade de todas as atividades de seus aplicativos conectados.   Como o conector do Office 365 já estava conectado, você poderá ver alguns dados. Depois de conectar o Cloud App Security a um aplicativo usando o conector de aplicativo, o Cloud App Security verifica todas as atividades que aconteceram — o período de verificação retroativa difere por aplicativo — e depois é atualizado constantemente com novas atividades.  

1. Selecione um item para exibir informações mais detalhadas. Observe na parte superior da página, a opção de adicionar uma nova política da pesquisa ou de exportar os dados para análise posterior.  Selecione **+Nova política da pesquisa**.  Observe como você pode criar uma política com base em um modelo, selecionar a gravidade e categoria de uma política, criar filtros para a política, criar alertas e até mesmo enviar os alertas para o Power Automate.  Selecione **Cancelar** para sair da janela de criação de política.

1. No painel de navegação esquerdo, selecione e explore a opção **Arquivos** e observe as opções para filtrar dados, criar uma política de arquivo e exportar os dados.  Selecione e explore a opção **usuário e contas**.  Observe as opções para filtrar e exportar os dados.

1. No painel de navegação esquerdo, selecione Configuração de segurança. Esta página fornece avaliações de configuração de segurança para suas contas do Azure, Amazon Web Services (AWS) e Google Cloud Platform (GCP).

1. Deixe essa página aberta para ser usada na próxima tarefa.


#### Demonstração – Parte 3: Nesta tarefa, você explorará as políticas e páginas de alertas no Microsoft Cloud App Security.

1. No painel de navegação esquerdo, em Controle, selecione **Políticas**.  As políticas listadas fornecem informações sobre o número de alertas gerados pela política, gravidade etc. A seleção de qualquer item de linha fornece informações mais detalhadas sobre a política. Selecione um item da lista, por exemplo, **Entrada suspeita**  

1. No painel de navegação esquerdo, selecione **Alertas**.  Se você tiver algum alerta listado, selecione um item da lista de alertas. Revise as informações fornecidas.  No canto superior direito da janela, selecione **Fechar alerta** para ver as opções de encerramento do alerta.  

1. Feche a janela do navegador.

#### Revisão
Nesta demonstração, você mostrou os recursos do Microsoft Cloud App Security.  Você mostrou as informações disponíveis no painel do Cloud Discovery, além dos recursos disponíveis para investigar as descobertas e controlar o impacto na sua organização por meio de políticas.
