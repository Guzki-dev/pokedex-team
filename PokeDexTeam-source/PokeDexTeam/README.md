# PokéDex Team — versão 10 (desenvolvimento)

Aplicativo Android híbrido com interface HTML/JavaScript local dentro de WebView.

## Novidades da versão 8
- Descrições de espécies priorizam o idioma português fornecido pela PokéAPI; se não houver tradução, a interface identifica o idioma disponível em vez de apresentar uma tradução inventada.
- Tipos apresentados em português com cores associadas a cada tipo na página de detalhes e comparação.
- Filtro de catálogo por jogo/geração como estimativa de espécies introduzidas até aquela geração.
- Novas abas: Favoritos, Comparar, Estatísticas e Caixas para organizar listas de Pokémon.
- A tela de Capturados calcula a porcentagem sobre o catálogo estimado da geração do jogo selecionado.
- As funções já existentes de equipes, captura, cache local e backup foram mantidas.

## Limitações importantes
- O filtro por geração é uma aproximação, não uma lista exata de disponibilidade por título. Remakes, jogos com Pokédex própria, spin-offs e ROM hacks precisam de bases específicas para garantir disponibilidade real.
- Comparação usa atributos-base; não calcula uma batalha completa.
- Favoritos e caixas são armazenados localmente no aparelho e devem ser incluídos em backup/exportação local.
- Descrições em português dependem de haver texto em português na fonte consultada.
- Mapas e encontros continuam limitados pela cobertura da fonte online.

## Compilar
Abra o repositório no GitHub e execute o workflow em `.github/workflows/android-apk.yml`. O artefato gerado precisa ser instalado e testado em aparelho Android antes de considerar a versão estável.


## Versão 9
- A ficha do Pokémon foi dividida em abas Resumo, Evoluções e Ataques.
- A linha evolutiva consulta a cadeia da PokéAPI e apresenta condições disponíveis (nível, item, troca, amizade, horário e outras condições retornadas).
- Descrições priorizam português da PokéAPI e, quando ausente, tentam tradução automática online com cache local; traduções automáticas devem ser conferidas.
- Navegação principal com botões em estilo cartão, estados ativos destacados e rolagem horizontal com encaixe.


## Versão 10
- Navegação principal em hub lateral, com seções de exploração, treinador e coleção; menu fecha ao selecionar uma aba ou tocar fora dele.
- A ficha individual mantém abas separadas para Resumo, Evoluções e Ataques.
- A linha evolutiva apresenta condições em português, com nomes traduzidos para vários itens comuns, e os cartões de evolução abrem a ficha da espécie selecionada.
- A descrição tenta usar texto em português da PokéAPI e, se indisponível, tenta tradução automática online e guarda a tradução no cache local. A tradução automática pode ter erros e exige internet na primeira consulta.
- Baseado no código-fonte da versão 9, preservando as funções existentes.


## Versão 11 (desenvolvimento)
- Mapas regionais apresentados como imagens estáticas, sem pontos interativos, com alternativa para abrir a página da região caso a imagem externa não carregue.
- Rotas e locais apresentados em lista numerada, com filtro e acesso aos encontros quando a API oferece dados. A ordem é natural por nome e a cobertura por jogo pode variar.
- Natureza configurável em cada Pokémon de equipe, com descrição do atributo aumentado e reduzido; naturezas neutras também são identificadas.
- Estatísticas da coleção mostram percentual capturado por jogo, usando o catálogo estimado por geração quando não há Pokédex específica validada.
- Imagens e dados externos dependem de conexão.

## Versão 12 (desenvolvimento)
- Habilidades dos Pokémon com descrições traduzidas para português quando disponíveis; tradução automática pode ser usada como alternativa.
- Seleção e salvamento de habilidade no editor de equipe.
- Filtros de Pokédex para Pokémon fósseis, Ultra Beasts e Pokémon Paradoxo.
- Área de Mega Evoluções e formas Gigantamax na aba Evoluções; a cobertura depende dos dados disponíveis na PokéAPI e do catálogo de formas especiais.

## Versão 17 — Hub principal
- Nova tela inicial com busca global por nome ou número, seletor do jogo de referência, atalhos e indicador de conexão.
- A seção “Continuar de onde parei” recupera a última aba visitada e a última ficha de Pokémon aberta.
- O menu lateral mantém as telas anteriores acessíveis e inclui o retorno ao Início.
- A seleção de jogo é salva localmente; equipes e progresso existentes não são apagados por esta atualização.
- O indicador online/offline explica que o modo offline depende dos dados previamente armazenados.
- Validação realizada: sintaxe JavaScript com `node --check`. A compilação Android e o teste no aparelho ainda precisam ser executados pelo workflow do GitHub.

## Versão 18 — integração de mapas e encontros
- As abas **Mapas** e **Encontros** agora abrem a mesma experiência integrada, com o jogo selecionado compartilhado.
- A lista de rotas/áreas permite abrir os encontros daquela área, com método, níveis e taxa informada pela PokéAPI quando disponível.
- Incluído botão para voltar ao mapa/lista depois de consultar uma área.
- Limitação: o mapa continua esquemático e a cobertura de encontros varia por versão. ROM hacks e spin-offs sem dados específicos não recebem encontros inventados; confirme detalhes específicos na Bulbapedia.
- Verificação feita nesta edição: sintaxe JavaScript (`node --check`) e integridade do ZIP. Não foi possível testar o APK em aparelho Android neste ambiente.
