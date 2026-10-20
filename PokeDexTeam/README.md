# PokéDex Team — projeto Android inicial

Protótipo Android baseado em WebView com interface em português, cache de Pokédex consultada, equipes persistidas localmente e calculadora básica de IV/EV para as fórmulas usuais das gerações III–IX.

## Como gerar o APK
1. Abra esta pasta no Android Studio (versão compatível com Android Gradle Plugin 8.7.3).
2. Aguarde a sincronização do Gradle e a instalação do Android SDK 35.
3. Use **Build > Build APK(s)** para gerar um APK de teste; o Android Studio mostrará o caminho do arquivo.

Este ambiente de criação não tem Android SDK/Gradle configurados, portanto o APK binário não foi compilado aqui. Este é o código-fonte inicial, não um APK pronto.

## Limitações atuais
- A Pokédex carrega nomes de Pokémon pela PokéAPI quando há internet e mantém o índice em cache; sprites são carregados da rede e podem depender do cache do WebView.
- Equipes ficam no armazenamento local do app; desinstalar o app apaga esses dados.
- A calculadora implementa a fórmula geral moderna e busca stats-base da PokéAPI; não é uma calculadora de IVs inferidos a partir de stats observados.
- Jogos e ROM hacks podem ter regras próprias. Os hacks são selecionáveis para organizar equipes, mas fórmulas/rosters exclusivos precisam ser configurados para cada hack.

## Funcionalidades adicionadas nesta revisão
- Aba Mapas com visualização esquemática ilustrativa e lista pesquisável de áreas usando o catálogo de location-area da PokéAPI quando disponível.
- Consulta de encontros por área, método e nível; a taxa é exibida conforme os dados retornados pela API e pode variar por versão.
- Acompanhamento local por jogo: faltando, visto ou capturado, disponível na Pokédex e nos encontros.
- ROM hacks continuam listados para organização, mas seus mapas e encontros precisam de fontes específicas e verificadas; não são inventados automaticamente.

## Limitações importantes dos mapas
A visualização atual é um mapa esquemático ilustrativo, não uma reprodução fiel dos mapas originais. O endpoint de áreas da PokéAPI é global e nem sempre oferece correspondência perfeita para todos os jogos/versões. Antes de tratar porcentagens como exatas, deve-se validar a versão e o método de encontro. ROM hacks exigem bases de dados específicas. A aba de mapas requer internet para buscar áreas e encontros novos, mantendo em cache a lista de áreas já carregada.

## Verificação desta entrega
- O JavaScript embutido em `app/src/main/assets/index.html` foi verificado com `node --check` e não apresentou erros de sintaxe.
- Não foi possível produzir/testar um APK neste ambiente porque o Android SDK e o Gradle executável não estão configurados aqui.
- A documentação oficial do Android Studio descreve a geração do APK em **Build > Build APK(s)**. Para um APK de distribuição, use **Build > Generate Signed Bundle / APK** e guarde a chave de assinatura em local seguro.

## Próximas tarefas antes de chamar de versão completa
1. Compilar no Android Studio com Android SDK 35 e validar em aparelho/emulador.
2. Ajustar a listagem de áreas para filtrar os locais por jogo/versão, validando as correspondências da PokéAPI.
3. Acrescentar mapas ilustrados próprios/licenciados por região e associar os pontos clicáveis aos locais.
4. Validar probabilidades por versão e método de encontro; não tratar `chance` isolada como probabilidade universal.
5. Adicionar datasets independentes e revisados para cada ROM hack, com identificação da versão do hack.
6. Testar fórmulas de IV/EV em cada geração e configurar exceções por ROM hack.

## Compilação gratuita na nuvem (sem computador próprio)
O workflow `.github/workflows/android-apk.yml` compila um APK de teste usando GitHub Actions. Para utilizá-lo, o projeto precisa estar em um repositório GitHub; no celular, abra o repositório, vá à aba **Actions**, escolha **Build Android APK** e toque em **Run workflow**. Quando terminar, abra a execução concluída e baixe o artefato `PokeDexTeam-debug-apk`. O uso gratuito depende dos limites e das condições atuais da conta GitHub. Esse workflow ainda precisa ser executado no GitHub para confirmar a compilação real.
