---
schema_version: "3.1"
tipo: ciclo
projeto: adrop
versao: v1
ciclo: c03
conhecimento: css-box-model
---

# c03 — css-box-model

A etapa do ciclo não é campo deste documento: o motor a deriva das evidências.

## Problema de contexto

- **P1.2 — Leitura confortável do post** (parte de espaço e largura): ao abrir o post com 360 px de largura, não há rolagem horizontal (RNF1); a capa e as imagens se ajustam à largura da coluna e nunca a ultrapassam (RNF3); no computador, o texto fica numa coluna centralizada com largura máxima (RNF4).
- **P2.1 — Apresentação e lista de posts** (parte de espaço e largura): com 360 px de largura, não há rolagem horizontal, e a capa do card cabe na coluna (RNF1, RNF3).

Hoje o N1 (`boasvindas.html`, `index.html` e `css/style.css`) já tem cores, fonte e foco do c02, mas nenhuma regra de largura ou de espaço. As três imagens têm 1000 × 1000 px: numa tela de 360 px, elas passam da tela e criam rolagem horizontal. No computador, o texto ocupa a largura inteira da janela. Este ciclo ensina como o navegador calcula o tamanho e o espaço de cada elemento, para que a aluna monte a coluna da Adrop e contenha as imagens nela.

## Objetivos de aprendizagem

- Ao fim do ciclo, a aluna consegue explicar que todo elemento é uma caixa com quatro camadas (conteúdo, padding, borda, margin) e dizer o papel de cada uma.
- Ao fim do ciclo, a aluna consegue distinguir elementos de bloco e de linha pelo jeito como ocupam a largura e prever onde `width`, `margin` e `padding` funcionam.
- Ao fim do ciclo, a aluna consegue calcular a largura total de uma caixa nos dois modos (`content-box` e `border-box`) e escolher o modo pelo motivo.
- Ao fim do ciclo, a aluna consegue montar uma coluna com largura máxima, centralizada no computador e sem rolagem horizontal no celular.
- Ao fim do ciclo, a aluna consegue conter imagens na largura da coluna, sem distorcer a proporção.
- Ao fim do ciclo, a aluna consegue usar o diagrama de caixa do F12 e a simulação de celular para descobrir de onde vem um espaço ou uma rolagem horizontal.

## O que será ensinado

1. A caixa: conteúdo, padding, borda e margin, do centro para fora; o diagrama de caixa do F12 (aba Computed).
2. Bloco × linha: quem ocupa a largura inteira e quem ocupa só o próprio conteúdo; o que isso muda para `width`, `margin` e `padding`; a propriedade `display` (`block`, `inline`, `inline-block`). A pedido da aluna, `display` recebe reforço forte e repetido: aparece no ensino técnico e em todos os N2, com previsão antes de testar.
3. As propriedades de espaço: `padding` e `margin`, com os atalhos de um a quatro valores e os lados (`-top`, `-right`, `-bottom`, `-left`); margens que o navegador já põe (`body`, `p`, títulos, `ul`, `figure`).
4. Largura: `width` × `max-width`; unidades `px`, `%` e `rem` para medidas de layout.
5. `box-sizing`: `content-box` (o padrão) × `border-box`, e a conta da largura total em cada um; a separação entre conceito (box model), propriedade (`box-sizing`) e valores (`content-box`, `border-box`). A pedido da aluna, também recebe reforço forte e repetido no ensino técnico e em todos os N2, com contas nos dois modos e o vocabulário certo.
6. Coluna centralizada: `max-width` com `margin` automático nas laterais; espaço interno no celular.
7. Imagens contidas: `max-width: 100%` e altura automática, sem distorcer.
8. Margens verticais que se juntam (colapso de margens), na medida em que aparecerem no post.
9. Conferência: simulação de celular no F12 (360 px), diagrama de caixa e caça à rolagem horizontal.

A profundidade de cada tópico será calibrada pelo diagnóstico (conhecimento declarado na entrevista).

## Resumo do ensino

### Diagnóstico (evidência 01)

- Firme: `padding` interno × `margin` externo como ideia geral; `max-width` como limite; imagem larga gera rolagem horizontal; espaço vindo da folha do navegador; F12 (Elements e Styles) para investigar.
- A ensinar desde a base: as quatro camadas da caixa e a borda como limite; bloco × linha e o efeito no `width`; a conta da largura total (padding e borda dos dois lados, margem fora; respondeu 332 em vez de 344); `box-sizing`; coluna com `max-width` e margens automáticas; imagens com `max-width: 100%` e altura automática (citou grid); diagrama de caixa (Computed) e simulação de celular.

### Ensino (evidência 02)

- Nove partes, uma por vez, a partir do N1 e dos RNF1, RNF3 e RNF4: a caixa e a borda como fronteira; bloco × linha e `display`; padding e margin (lados, atalho no sentido do relógio, margens do navegador); a conta da largura; `box-sizing`; a coluna (`max-width`, `margin` `auto`, padding lateral); imagens contidas; colapso de margens; F12 (360 px, realce, roteiro da rolagem).
- Experimentos no F12, sem alterar arquivos: margem de 8 px do `body`, contorno vermelho em todos os elementos, `width: 300px` no `h1` × no link, causa da rolagem a 360 px (imagem de 1000 num `article` de 344), margem de 40 px da `figure`.
- Pedidos da aluna: reforço forte e repetido em `display` (`block`, `inline`, `inline-block`) e em box model × `box-sizing` × `content-box`/`border-box`, no ensino técnico e em todos os N2.
- Precisaram de reforço: margem do `body` atribuída à herança do `header`; como classificar um elemento como inline (a tag decide, não o lugar); "declaração" × "valor"; `display: block` tido como condição do `height: auto` na imagem; números junto com o raciocínio.

### Verificação teórica (evidência 03)

- 2/5, sem erro estrutural: insatisfatória ("ainda não").
- Firme: camadas e borda como fronteira; pintura do fundo; conteúdo em `border-box`; box model × `box-sizing` × valores (papéis); coluna com `max-width` e `auto` pela sobra do pai.
- A reforçar: papel de cada camada; em inline, `width` e margem vertical ignorados, mas padding e margem laterais funcionam; margem fora da medida até a borda (somada de novo, como no 332 do diagnóstico); porcentagem + padding em `content-box` (sem resposta na Q5); propriedade × declaração × regra.
- Próximo passo: novo `ensino` focado nesses aspectos e depois uma verificação teórica nova, com perguntas diferentes.

### Reensino focado (evidência 04)

- Cinco partes, com previsão antes de testar: inline em dois eixos ("deitado funciona, em pé não empurra, tamanho é do texto"), `width` como tamanho e não espaço, o inline quebrado em pedaços, beiradas só nas pontas e `inline-block` (teste no `span.logo` do rodapé); as duas medidas e como ler qual a pergunta pede; roteiro do estouro (pai → quanto oferece → `box-sizing` → somar e comparar); papel de cada camada; regra × declaração × propriedade × valor.
- Firme: as quatro previsões do inline, conferidas no F12; 150 e 200 no `.selo`; o roteiro aplicado sem ajuda no `.aviso` (28 px); papéis das camadas; nomes das partes da regra.
- A reforçar: ler qual medida a pergunta pede ("pintado" contou só o fundo); não descontar o `body` de um espaço já dado; "modo" trocado por "`box-sizing`" no roteiro.
- Próximo passo: verificação teórica nova, com perguntas diferentes.

### Verificação teórica, segunda (evidência 05)

- 5/5, sem erro estrutural: satisfatória (porta 1).
- Firme: papel das camadas e cor do espaço novo; lados do inline × `inline-block`; medidas em `border-box` com porcentagem; colapso de margens (vertical junta, lateral soma); coluna no computador com `max-width`, padding em `content-box` e margens `auto`, com o roteiro encadeado sem ser pedido.
- A reforçar no ensino técnico: "herda" para o fundo do próprio elemento; padding vertical do inline é pintado, não "sem efeito"; `inline-block` que não cabe desce de linha.
- Próximo passo: ensino técnico, com o reforço forte de `display` e `box-sizing` pedido pela aluna.

### Ensino técnico (evidência 06)

- Cinco partes, com ajuda decrescente, em blogs fictícios: reforços (fundo próprio × herança; padding vertical do inline pintado sem empurrar; `inline-block` que não cabe desce inteiro), leitura de uma folha pronta, 14 lacunas, quatro reclamações para corrigir e um pedido de nove itens escrito do zero. Testes só no F12.
- Firme: contas nos dois modos com o caminho das caixas à vista (376 × 312); colapso de margens; `max-width: 100%` × `width: 100%` na imagem; `inline-block` para padding vertical que empurra; regra direta no `header a` (ligação com o c02).
- Lacuna tratada aqui: `display: block` tido como condição do `height: auto` na imagem; caiu com o teste no `index.html`.
- A observar nos N2: padding vertical do inline ainda descrito como "sem efeito" quando misturado a outras ideias; atalhos de um e dois valores (quais lados); `block` × `inline-block` na escolha; precisão (unidade, acento no seletor, item esquecido); desenhar a árvore das caixas antes de calcular.
- A aluna recusou uma atividade de contas extra, anunciada depois da última parte: etapas anunciadas devem ser cumpridas, e repetição de algo já demonstrado cansa.
- Próximo passo: N2.1 (fixação).

### Treino 1 — fixação (evidência 07)

- Coluna e imagens contidas no post "Como nasce um hábito" (do c02), com duas previsões antes do teste (`box-sizing` e `display`).
- Satisfatório e autônomo: ajuda máxima pergunta orientadora.
- Firme: previsões de `box-sizing` (672 × 640) e de `display` (`inline` pinta sem empurrar, `block` ocupa a largura toda); coluna, imagens, `figure` e botão em `inline-block`.
- A observar: lado da margem no pedido (`margin-bottom` para "só em cima"); leitura do diagrama do Computed (o número do meio é só o conteúdo).
- Próximo passo: N2.2 (variação).

### Treino 2 — variação (evidência 08)

- Página de cards do tema Neurociência (do c02): cards com borda, respiro e distância, listas dentro de listas e etiqueta em `inline-block` no cabeçalho.
- Previsões escritas retiradas do enunciado a pedido da aluna (o N2 mede aplicação; teoria já demonstrada). Daqui em diante, N2 só com pedidos de código e conferência.
- Satisfatório e autônomo: ajuda máxima esclarecimento (de onde copiar os arquivos).
- Firme: os oito pedidos na primeira entrega; atalhos de um e dois valores; lado da margem (`margin-bottom` para "até o card de baixo"); `block` na imagem × `inline-block` na etiqueta.
- Próximo passo: N2.3 (transferência).

### Treino 3 — transferência (evidência 09)

- Receita do bolo de cenoura no "Sabor de Casa" (do c02): leitor cozinhando, foto dentro de um passo de lista numerada, valores escolhidos pela aluna.
- Satisfatório e autônomo: ajuda máxima pergunta orientadora (reformulada uma vez, com o sintoma descrito).
- Firme: três escolhas de `display` pelo motivo (aviso inline pintado sem empurrar, botões `inline-block`, botão de voltar `block`); foto do passo com `max-width` e `margin` `auto` na `figure`; coluna e fotos contidas.
- A observar: alcance do seletor ao trocar o `display` (`li` alcançou todas as listas; `ul, ol` tirou recuos não pedidos); classes acrescentadas no HTML contra o enunciado; conferir a página inteira, não só o item.
- Próximo passo: verificação técnica (porta 3 depois da porta 2).

### Verificação técnica (evidência 10)

- 2/5, sem erro estrutural: insatisfatória ("ainda não").
- Firme: atalhos e lados; `max-width` × `width` na coluna e nas imagens, `height: auto`; o roteiro da conta aplicado sem pedido.
- A reforçar: padding vertical do `block` empurra (dado como "não afeta a faixa"); alcance do seletor ao trocar o `display` (`a` em vez de `nav a`); porcentagem sobre o conteúdo do pai em `border-box` com padding (30% de 640 em vez de 600); margem do primeiro filho que vaza do pai sem padding nem borda em cima (sem resposta).
- Cores em hexadecimal nos enunciados atrapalham: nomear a cor junto.
- Próximo passo: novo `ensino-tecnico` focado nesses quatro aspectos e depois uma verificação técnica nova, com perguntas diferentes.

### Ensino técnico focado (evidência 11)

- Quatro partes, uma por aspecto da evidência 10, com mapa visual e uma pergunta curta em cada: margem do primeiro filho que vaza (a pedido da aluna, primeiro); padding vertical que empurra em `block`; alcance do seletor ao trocar o `display`; porcentagem sobre o conteúdo do pai, com o roteiro em cinco passos.
- A pedido da aluna: onde vai o `display` ("o `display` fala de mim, não dos meus filhos"; `ul` × `li` em `inline-block`; no flexbox, ao contrário, o pai organiza).
- Firme: as quatro perguntas certas de primeira.
- A observar: o seletor limitado ainda não é automático em exemplo pequeno (`li` em vez de `.tags li`); o `display` no elemento que se move.
- Próximo passo: verificação técnica nova, com perguntas diferentes.

### Verificação técnica, segunda (evidência 12)

- 0/5, sem erro estrutural: insatisfatória ("ainda não"). Encerrada pela aluna com a Q3 apresentada; Q4 e Q5 não apresentadas. Sessão depois da meia-noite, depois de muitas atividades seguidas.
- Firme: borda e lado; margem transparente com o fundo do pai; afastamento lateral do inline; `inline-block` para o padding vertical empurrar.
- A reforçar: ordem do atalho de quatro valores (esquerda × direita); margem vertical do inline ignorada, sem colapso (o colapso pai-filho, recém-ensinado, foi estendido ao inline); padding como parte do fundo pintado (contado como espaço vazio).
- A aluna pediu ensino só expositivo, sem exercícios por parte; verificações e N2 seguem obrigatórios.
- Próximo passo: ensino técnico expositivo nesses três aspectos; verificação técnica nova numa sessão descansada.

### Ensino técnico expositivo (evidência 13)

- Três pontos, só explicação, sem exercícios: relógio do atalho de quatro valores ("a esquerda fica por último"); margem vertical do inline ignorada, colapso só entre blocos; padding dentro do fundo pintado ("só o transparente é distância").
- Dúvidas da aluna: o padding nunca colapsa, mas a pintura do inline pode passar da beirada do pai; pai com padding ou borda soma por dentro, pai só com margem colapsa e vale a maior.
- Próximo passo: verificação técnica nova, a pedido da aluna na mesma sessão, com cinco perguntas de um item só.

### Verificação técnica, terceira (evidência 14)

- 4/5, sem erro estrutural: satisfatória (porta 3).
- Firme: atalho de três valores; inline com margem vertical ignorada e padding pintado sem empurrar; porcentagem sobre o conteúdo do pai, na ordem do roteiro; colapso pai-filho com a maior margem.
- A observar no N1: estouro medido pela borda direita (ponto de partida dentro do padding do pai + largura), não só pela largura (12 em vez de 28).
- Formato que funcionou: perguntas de um item só, diretas.
- Próximo passo: apto para N1, com os desafios de N1 escritos neste ciclo.

### Desafios no projeto (evidência 15)

- Dois desafios: P1.2 (coluna, respiro e imagens do post) e P2.1 (mesma coluna na página inicial e capa do card contida), com RNF1, RNF3 e RNF4.
- A observar na aplicação: alcance do seletor nas `ul` aninhadas; estouro pela borda direita; margem da `figure`; HTML sem mudança.
- Próximo passo: a aluna aplica no N1, faz o commit e roda `estudos avaliar`.

## N2

Os treinos ficam em `Treinos/`, ao lado deste arquivo:

- n2-1: `Treinos/Treino 1 - fixação/`
- n2-2: `Treinos/Treino 2 - variação/`
- n2-3: `Treinos/Treino 3 - transferência/`

Nova tentativa: `Treino 2 - variação - tentativa 2`.

## Desafios de N1

### P1.2 — Coluna e imagens do post

**Objetivo:** quem abre o post lê sem rolar para os lados no celular e numa coluna centralizada no computador.

**Arquivos:** `css/style.css`, `boasvindas.html`

#### Tarefas

- [ ] 1. Escolha como as caixas do site medem a largura e aplique a todas.
- [ ] 2. Ponha o conteúdo do post numa coluna centralizada, com largura máxima em `rem`.
- [ ] 3. Dê à coluna um respiro lateral para o texto não encostar na tela do celular.
- [ ] 4. Faça a capa e as imagens das figuras caberem na coluna, sem distorcer.
- [ ] 5. Confira no diagrama de caixa (Computed) os espaços que o navegador pôs e decida quais ficam.
- [ ] 6. Confira o post na simulação de 360 px e numa janela larga, item por item do "Pronto quando".

#### Pronto quando

- [ ] A 360 px, não há rolagem horizontal, e nenhuma caixa passa da borda direita da tela no realce do F12 (RNF1).
- [ ] A capa e as duas imagens das figuras cabem inteiras na coluna, sem ficar achatadas, a 360 px e numa janela larga (RNF3).
- [ ] Numa janela larga, o conteúdo fica numa coluna centralizada, com o mesmo espaço vazio dos dois lados (RNF4).
- [ ] A 360 px, o texto não encosta nas laterais da tela.
- [ ] Nenhuma declaração com ⚠️ no Styles, e as listas e os links que não estão nos pedidos continuam como antes.
- [ ] O `boasvindas.html` não mudou.
- [ ] O post aparece igual no Chrome e no Edge, aberto com dois cliques (RNF10).

#### Não fazer

- Flexbox, grid e media queries: ficam fora da V1.
- Mudar cores, fontes, contraste ou foco do c02.

### P2.1 — Página inicial e card na coluna

**Objetivo:** quem abre a página inicial no celular vê a apresentação e o card do post sem rolar para os lados, com a capa dentro do card.

**Arquivos:** `css/style.css`, `index.html`

#### Tarefas

- [ ] 1. Confira no Styles quais regras do post já atingem a página inicial.
- [ ] 2. Crie regra nova só para o que nenhuma regra existente resolve.
- [ ] 3. Faça a capa do card caber na coluna, sem distorcer.
- [ ] 4. Confira a página inicial na simulação de 360 px e numa janela larga, item por item do "Pronto quando".

#### Pronto quando

- [ ] A 360 px, não há rolagem horizontal, e nenhuma caixa passa da borda direita da tela no realce do F12 (RNF1).
- [ ] A capa do card cabe inteira na coluna, sem ficar achatada (RNF3).
- [ ] Numa janela larga, a apresentação e a seção "Posts" ficam na mesma coluna centralizada do post (RNF4).
- [ ] Mudar a largura máxima da coluna no CSS muda as duas páginas.
- [ ] Nenhuma declaração com ⚠️ no Styles.
- [ ] O `index.html` não mudou.

#### Não fazer

- Borda, sombra ou fundo no card: a V1 não pede.
- Flexbox, grid e media queries: ficam fora da V1.
