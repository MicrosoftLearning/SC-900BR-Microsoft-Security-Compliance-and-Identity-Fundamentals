---
Demo:
    title: 'Central de Segurança do Azure'
    module: 'Módulo 3 – Lição 2: Descrever os recursos das soluções de segurança da Microsoft: Descrever os recursos de gerenciamento de segurança do Azure'
---

# Demonstração: Central de Segurança do Azure

### Cenário da demonstração

Nesta demonstração, você verá a Central de Segurança do Azure e mostrará como o Azure Secure Score pode ser usado para melhorar a postura de segurança de uma organização.

1. Abra a guia do navegador, **Página Inicial – Microsoft Azure**.  Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e entre novamente.

1. Na caixa de pesquisa, na barra azul, na parte superior da página, ao lado de onde está escrito Microsoft Azure, insira **central de segurança** e selecione **Central de Segurança** nos resultados da pesquisa.

1. Se esta for a primeira vez que você entra na Central de Segurança com sua assinatura, você pode acessar a página de introdução e pode ser solicitado a atualizar.  Role até a parte inferior da página e selecione **Pular**.

1. Observe as informações disponíveis na página de visão geral da Central de Segurança.  Observação: Você pode ver uma caixa de informações azul na parte superior da página indicando que você pode estar vendo informações limitadas.  Não a selecione (pode levar até 15 minutos para processar e não faz diferença para esta demonstração).

1. As informações na parte superior da página incluem o número de assinaturas do Azure, o número de Recursos avaliados, o número de recomendações ativas e outros alertas de segurança.  No corpo principal da página, há cartões que representam Secure Score, Conformidade regulatória, Insights, Azure Defender e muito mais.  

1. Na parte superior da página, selecione **Recursos avaliados**.  (Observe que isso equivale a selecionar Inventário no painel de navegação esquerdo da página inicial da Central de Segurança).
    1. Essa ação leva você para a página **Inventário** que mostra sua assinatura do Azure Pass.  Selecione **Azure Pass – Sponsorship**.
    1. A página Resource Health fornece uma lista de recomendações.  Na lista disponível, selecione **Deve haver mais de um proprietário atribuído à sua assinatura**.
    1. Selecione a seta suspensa ao lado de Etapas de correção. Observe como as etapas de correção detalhadas são fornecidas junto com a opção de ação.  
    1. Selecione **Central de Segurança** no canto superior esquerdo da tela para retornar à página de visão geral da Central de Segurança.

1. Na parte superior da página, selecione **Recomendações ativas**.  (Observe que isso equivale a selecionar Recomendações no painel de navegação esquerdo da página inicial da Central de Segurança).
    1. A página de recomendações mostra o painel do Secure Score. 
    1. Abaixo do painel do Secure Score, há uma lista de controles. Cada controle de segurança representa um risco de segurança que deve ser mitigado e também inclui informações sobre a pontuação máxima associada a esse controle, a pontuação atual, o aumento potencial da pontuação e o status da integridade do recurso.  
    1. Selecione um dos controles, por exemplo **Habilitar MFA**.  Selecione um dos subitens, por exemplo **A MFA deve ser habilitada em contas com permissões de proprietário em sua assinatura**.  Na página que é aberta, você verá uma descrição, etapas de correção e recursos afetados. Feche a página selecionando o **X** no canto superior direito da tela.
    1. Feche a página de recomendações clicando no **X** no canto superior direito da tela para voltar à página de visão geral.

1. Você está de volta à página Visão geral da Central de Segurança.  Na página principal, selecione Secure Score (isso é equivalente a selecionar Secure Score no painel de navegação esquerdo).
    1. Essa ação o leva ao Painel do Secure Score.  Além disso, lista todos os grupos de gerenciamento e assinaturas disponíveis.  Selecione sua assinatura do Azure – Azure Pass – Sponsorship.
    1. Essa ação leva à página Recomendações, que foi mostrada anteriormente.
    1. Feche a página de recomendações selecionando o **X** no canto superior direito da tela.
    1. Feche a página do Secure Score selecionando o **X** no canto superior direito da tela para voltar à página de visão geral.

1. Você está de volta à página Visão geral da Central de Segurança.  Na página principal, selecione **Conformidade regulatória**. (Observe que isso equivale a selecionar Recomendações no painel de navegação esquerdo da página inicial da Central de Segurança).
    1. A página de conformidade regulatória fornece uma lista de controles de conformidade.  Em cada controle, está um conjunto de avaliações baseadas no parâmetro de comparação de segurança do Azure, que fornece recomendações sobre como você pode proteger suas soluções de nuvem no Azure.
    1. Selecione **IM. Gerenciamento de Identidades** e selecione **IM.4 Usar controles de autenticação forte para todos os acessos baseados no Azure Active Directory**.  A lista mostra as ações de responsabilidade do cliente que podem ser tomadas para melhorar a postura de conformidade.
    1. Selecione o **X** no canto superior direito da tela para fechar a página e retornar à página de conformidade regulatória.
    1. Selecione o **X** no canto de superior direito da tela para voltar à página de visão geral.

1. Retorne à página inicial do portal do Azure selecionando **Página Inicial** no canto superior esquerdo da página.  Mantenha esta guia do navegador disponível para voltar a ela em uma demonstração posterior.

## Revisão

Nesta demonstração, você mostrou a Central de Segurança do Azure e mostrou como o Azure Secure Score pode ser usado para melhorar a postura de segurança de uma organização.
