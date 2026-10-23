# Gundamdex: Operação Cometa Vermelho

## Direção do projeto

O Gundamdex é primeiro um catálogo visual da franquia Gundam. A página inicial deve abrir no catálogo: busca, cartões com ilustrações individuais e uma ficha detalhada da unidade selecionada. O catálogo também abastece as fichas do RPG.

A interface usa um fundo espacial azul profundo com estrelas, cartões e fichas em tons escuros, mantendo as ilustrações das unidades em destaque.

## Cobertura da base atual

- 828 registros distintos importados da API comunitária consultada em 23/10/2026.
- 809 registros têm uma imagem vinculada na fonte; 19 aparecem com fallback visual.
- Campos locais: identificador da fonte, nome, pilotos informados, URL da imagem e URL da página de referência.
- Busca por nome ou piloto, filtro por disponibilidade de imagem e ordenação.
- Cada ficha oferece link para conferir a página de referência.
- A base usada para popular a tela está em catalog.gundams.json e também é embutida no index.html para o protótipo abrir diretamente no navegador.

Fonte: [Gundam API](https://gundam-api.pages.dev/), uma API não oficial que compila conteúdo do Gundam Wiki/Fandom. A contagem e a cobertura refletem essa fonte, não um inventário oficial completo. Os registros ainda precisam de revisão para detectar ausências, variantes duplicadas e casos fora do escopo. As imagens carregam diretamente do host externo do Gundam Wiki/Fandom; não foram copiadas para este projeto.

## Escopo do protótipo v0.2

- Catálogo é a primeira página e contém 828 registros pesquisáveis.
- Painel de detalhes com nome, pilotos disponíveis e link da fonte.
- Integração catálogo → ficha: qualquer Gundam selecionado pode ser levado ao RPG.
- Ficha de piloto com quatro atributos e orçamento de 8 pontos.
- Missão de escolta com três encontros, terminando no confronto contra Char Aznable, o Cometa Vermelho, em seu Zaku II vermelho.
- Regras acessíveis pela navegação.
- A abertura apresenta Gundam; ao preparar a missão, Char Aznable surge em uma transmissão animada.

## Regras provisórias do RPG

### Atributos

- **Tiro:** usado com o rifle.
- **Combate:** usado com o sabre.
- **Pilotagem:** soma à Defesa contra ataques inimigos.
- **Tática:** soma ao reparo.

A criação distribui exatamente 8 pontos entre os atributos, cada um de 0 a 4.

### Unidade no protótipo

O catálogo não fornece estatísticas equilibradas para RPG. Por isso, todas as unidades começam com parâmetros temporários iguais: Integridade 24, ataque +1 e Defesa 13. Eles são regras de jogo próprias e podem mudar quando fizermos o balanceamento.

### Combate

- **Rifle:** d20 + Tiro + bônus de ataque da unidade + 1; acerta se igualar ou superar a Defesa inimiga; causa 4 de dano.
- **Sabre:** d20 + Combate + bônus de ataque da unidade; acerta se igualar ou superar a Defesa inimiga; causa 6 de dano.
- **Crítico:** resultado natural 20 acerta e soma 2 de dano.
- **Falha crítica:** resultado natural 1 sempre erra.
- **Evasão:** acrescenta +4 à Defesa contra a próxima resposta inimiga.
- **Reparo:** uma vez por missão, restaura 1d6 + Tática de Integridade, até o máximo.

Depois da ação do piloto, um inimigo ativo rola d20 + ataque contra Defesa da unidade + Pilotagem do piloto. Derrotar os dois guardas e Char Aznable conclui a escolta; se a Integridade chegar a zero, a missão termina em derrota. O próximo inimigo entra sem ataque imediato.

## Próximas etapas

1. Auditar a cobertura e a nomenclatura do catálogo, usando a referência comunitária e fontes oficiais por série.
2. Adicionar universo/linha temporal, série, designação, variante, facção, altura, peso, armamentos e relações entre unidades com fonte por campo.
3. Recuperar imagens ausentes ou substituir seus cartões por arte autorizada.
4. Rever atribuições de pilotos e remover entradas que não sejam Gundams jogáveis.
5. Balancear parâmetros de jogo por unidade e montar mais missões.
6. Migrar a base para banco de dados e desenvolver filtros e fichas persistentes.

## Arquivos

- index.html: protótipo autocontido para navegador.
- README.md: apresentação do projeto e instruções para abrir.
- catalog.gundams.json: dados importados da API de referência.
- ESCOPO-REGRAS.md: direção, proveniência, escopo e regras provisórias.

Projeto de fã, sem afiliação com Bandai Namco. Marcas, ilustrações e nomes pertencem a seus respectivos titulares.