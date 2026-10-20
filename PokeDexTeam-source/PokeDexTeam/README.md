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
