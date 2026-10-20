# PokéDex Team — versão 8 (desenvolvimento)

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
