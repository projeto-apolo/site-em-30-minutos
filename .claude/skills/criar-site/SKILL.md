---
name: criar-site
description: >
  Cria o site ou landing page de um cliente. Use sempre que a tarefa for "criar
  site", "fazer landing page", "montar a página", "site do cliente X" ou
  variações. Cobre desde página única até site institucional, sempre com
  qualidade de design profissional e alinhado à identidade DO CLIENTE.
---

# Skill: Criar Site

Objetivo: entregar sites que pareçam **feitos sob medida** — nunca "template de
agência genérico". Cada site deve transmitir a essência daquele negócio: uma
clínica parece clínica, um restaurante parece restaurante.

É aqui que o método se prova. Um site que parece caro é o que sustenta o preço
cobrado, gera indicação e vira portfólio. Um site genérico faz o cliente
perguntar por que não usou um construtor gratuito.

## A régua: os 8 pilares de um site "caro"

O que separa um site de R$ 10 mil de um de R$ 200 são **8 pilares**, em três
grupos. Use como régua do início ao fim — toda decisão serve a um deles.

**Gosto**
1. **Ponto de vista** — uma direção real, não um amontoado de referências. O site
   tem opinião visual e fala de UM negócio específico.
2. **Tipografia** — par display + corpo com personalidade. Nunca Inter, Roboto
   ou Arial como título (ver Fase 1).
3. **Cor** — paleta restrita e intencional: 1 dominante + 1 acento. Restrição
   sinaliza qualidade; arco-íris e neon sinalizam amador.
4. **Hierarquia** — o tamanho de cada elemento diz ao olho o que ler 1º, 2º, 3º.
   Sem isso o site fica chapado e difícil de escanear.

**Substância**
5. **Imagem** — fotos e visuais reais, adequados ao negócio (ver Fase 2).
6. **Copy** — texto com **restrição**: concreto e sensorial, poucos adjetivos.
   "Ribeye maturado 60 dias, na brasa" vale mais que "deliciosa carne premium de
   altíssima qualidade".

**Qualidade percebida**
7. **Mobile desenhado** — não só "responsivo/encolhido", pensado de fato para o
   telefone (ver Fase 3). O cliente vê mais no celular que no computador.
8. **O "invisível"** — o que faz o site *sentir-se* caro: micro-interações,
   movimento sutil, elementos que aparecem de forma escalonada, sensação de
   rápido e acabado. É a diferença entre *parecer* caro e *sentir-se* caro.

> No fim do build, **avalie o site honestamente contra os 8 pilares** (Fase 4).

## Regra de ouro — a identidade é DO CLIENTE

**Toda entrega segue a identidade visual do cliente, não a da agência.** Extraia
paleta, logo e tom da marca dele (do site atual, da logo, das fotos, do
`CLIENTE.md`).

A identidade da agência (`agencia/identidade.md`) serve para as peças da própria
agência — propostas, apresentações. Nunca é imposta na entrega do cliente.

Se o cliente não tem identidade definida, proponha uma coerente com o segmento
dele. Comece pelo arquivo do ramo em `agencia/nichos/`, se houver.

## Antes de começar (obrigatório)

1. Confirme **qual cliente** e leia `clientes/<cliente>/CLIENTE.md`.
2. Leia `agencia/stack.md` e, se existir, `agencia/nichos/<ramo>.md`.
3. Veja o que tem em `clientes/<cliente>/assets/` (logo, fotos, textos).
4. Se o cliente tem site atual, **analise-o**: o que reaproveitar (conteúdo) e o
   que melhorar (design, mobile, conversão).
5. **Referências visuais** — junte 3 a 5 antes de codar. Peça exemplos de sites
   que o cliente gosta; na falta, busque referências do segmento. Não é para
   copiar, é para alinhar gosto. É muito mais fácil *mostrar* o que se quer do
   que descrever em palavras.

## Fase 1 — Sistema visual (sempre, antes de codar)

Defina o sistema por escrito ANTES de escrever qualquer HTML.

- **Direção/conceito:** comprometa-se com UMA ideia que expresse o negócio
  (clínica → "precisão, calma, confiança"). Intencionalidade vence intensidade.
  - **Ofereça 2–3 direções nomeadas** antes de codar (para um restaurante:
    "sóbrio e dramático" vs. "moderno e claro" vs. "clássico acolhedor"). Deixe
    o operador escolher — é a decisão que mais define o site, e a que mais evita
    retrabalho.
- **Cor:** paleta da marca do cliente. 1 dominante + 1 acento usado com
  parcimônia (botões, destaques). Fundo com temperatura sutil, **nunca branco
  puro chapado**. Garanta contraste AA (4.5:1 em texto).
  - Ponto de partida por segmento (não é regra): saúde → azul/teal; jurídico e
    financeiro → navy com acento sóbrio; alimentação → tons quentes; tecnologia →
    escuro com acento vivo; beleza e bem-estar → tons suaves. Evite roxo em
    branco genérico e evite neon.
- **Tipografia:** par display + corpo com personalidade.
  - **Inter é a fonte "cara de IA" número 1.** Se ela aparecer no resultado,
    troque (Geist, Manrope, Figtree). Idem Roboto e Arial como título.
  - Sugestões por clima: saúde → Figtree/Lexend + Source Sans; corporativo →
    Lexend + Source Sans; moderno → Sora/Bricolage + Manrope; editorial →
    serifada display + sans no corpo.
  - Escala consistente (ex.: 12/14/16/20/25/31/39/49).
- **Hierarquia:** o tamanho guia a leitura (nome enorme → detalhe médio →
  descrição pequena). Não é tamanho aleatório.
- **Espaçamento:** ritmo de 8pt. Respiro generoso entre seções.
- **Ícones:** UMA família de ícones SVG de traço consistente. **Nunca emoji como
  ícone.**
- **Profundidade:** evite fundo chapado. Com sutileza: textura de pontos,
  gradiente radial suave, linhas finas, sombras coerentes.

## Fase 2 — Estrutura, conteúdo e espaços para imagem

Estruture as seções e **valide com o operador antes de codar**.

- **Comece pelo texto do hero, não pelo visual.** Erro comum: montar a imagem
  primeiro e depois não achar um tratamento de texto que case. Feche primeiro o
  layout de texto do hero (headline, hierarquia, copy) e construa o visual ao
  redor dele. O visual serve à mensagem.
- **Seções típicas (institucional):** header fixo + navegação responsiva → hero
  com proposta de valor + botão → faixa de prova/confiança → serviços →
  diferenciais → sobre → equipe → chamada final → contato/mapa → rodapé.
- **Padrão de conversão (negócio local):** hero credível → prova (números,
  certificações, depoimentos) → oferta clara → botão de WhatsApp.
- **Copy:** tom do cliente, sem placeholder.
  - **Escreva com restrição.** A tendência natural é explicar demais, empilhar
    adjetivos e tentar soar impressionante. Faça o oposto: concreto, sensorial,
    poucas palavras. "6 pratos, 1 fogo" vale mais que um parágrafo.

### Espaços para imagem (obrigatório)

Todo site precisa de **lugares planejados para fotos reais**. Um site de clínica,
restaurante ou prestador de serviço sem imagem parece incompleto.

- Reserve áreas para: **hero** (ambiente ou composição), **sobre/fachada**,
  **equipe** (retratos), **galeria/serviços**, e fundos de seção quando couber.
- Onde ainda não há foto real, crie um **placeholder elegante e marcado** — não
  um retângulo cinza vazio. Área com proporção definida (`aspect-ratio`), cor da
  marca, ícone e rótulo do que vai ali ("Foto da fachada", "Equipe").
- Liste no `CLIENTE.md` → próximos passos quais imagens o cliente precisa enviar.
- **Foto profissional é sempre o ideal.** Não havendo, **gerar imagem por IA é
  um caminho válido** para hero e seções enquanto a real não chega. Truque: peça
  ao Claude para **escrever o prompt da imagem** com base no projeto (paleta,
  direção, segmento) — ele já tem o contexto e acerta mais rápido. Trate a
  imagem gerada com o mesmo cuidado de uma real (proporção, `alt`, otimização).
- Performance: `loading="lazy"` abaixo da dobra, `width`/`height` ou
  `aspect-ratio` para evitar o layout pulando, WebP/AVIF quando for foto real.

## Decisão de tecnologia

- **Página única / institucional** → HTML + CSS + JS puro. Rápido, fácil de
  publicar, e é o padrão para negócio local.
- **Site com mais interatividade** → React + Vite + Tailwind, com os tokens da
  marca do cliente.

Ver `agencia/stack.md`. Na dúvida entre os dois, escolha o primeiro: quase todo
negócio local é bem servido por ele, e é muito mais fácil de manter.

> **Componentes prontos como inspiração:** bibliotecas de efeitos (scroll,
> cursor, animação) servem como **referência de ideia**. Mas **proteja a
> arquitetura**: não cole um componente React num site em HTML puro — recrie o
> efeito na tecnologia do projeto. A complexidade do projeto define a stack, não
> o componente bonito que você encontrou.

### Movimento avançado (3D, scroll) — com critério

Dá para fazer sites com elementos 3D e animação guiada por scroll. Mas é faca de
dois gumes:

- **Use quando o segmento pede "uau":** tecnologia, produto, imobiliário de
  alto padrão, eventos, portfólio, lançamento. Ali o espetáculo vende.
- **Evite em segmentos de confiança:** saúde, laboratório, jurídico, contábil,
  financeiro. Ali credibilidade e **velocidade** valem mais que espetáculo — um
  3D pesado parece deslocado e ainda derruba o desempenho. Prefira movimento
  discreto.
- **Desempenho e acessibilidade mandam:** nunca travar o scroll, sempre
  respeitar `prefers-reduced-motion`, sempre ter alternativa no celular.

**Técnica do elemento-âncora (vale mesmo sem 3D):** pegue o elemento visual
grande do hero e reaproveite-o na transição para a próxima seção — ele se move ou
escala conforme o scroll e "costura" as duas. Dá coesão e sensação premium. Pode
ser uma imagem, uma forma da marca ou uma ilustração leve.

## Fase 3 — Implementação

1. Gere os arquivos em `clientes/<cliente>/site/`.
2. Defina os tokens da marca em `:root` (cores, fontes, espaçamento, raio,
   sombra) — uma única fonte da verdade, nunca cor solta espalhada pelo código.
3. Mobile-first sempre. Teste mentalmente em 375 / 768 / 1024 / 1440.
4. Micro-interações sutis (150–300ms). Um carregamento com elementos surgindo de
   forma escalonada vale mais que mil animações. Respeite
   `prefers-reduced-motion`.
   - **Passada de "qualidade percebida" (pilar 8):** com a estrutura pronta,
     percorra **seção a seção** e ache as que ficaram chapadas. Para cada uma,
     acrescente **uma** interação sutil. Uma por seção, sempre discreta — se
     ficar óbvia ou barulhenta, refaça mais sutil. É essa camada que faz o site
     se sentir caro.
5. **Passada dedicada de celular (pilar 7):** responsivo não é o mesmo que
   desenhado para telefone. Faça uma passada só de mobile decidindo, por seção,
   **o que esconder, o que apertar e o que redimensionar** (menu colapsa,
   espaçamento mais justo, botões menores, hero recomposto). O cliente vai abrir
   no celular — trate isso como design, não como encolhimento.
6. SEO básico: `<title>`, meta description, Open Graph, `lang`, favicon, `alt`
   em todas as imagens.
7. Acessibilidade: contraste AA, foco visível (`:focus-visible`), labels reais
   nos formulários, `aria-label` em botão só com ícone, hierarquia de títulos.

## Fase 4 — Auto-avaliação e polimento

Com a primeira versão pronta, **não entregue ainda**. É este passo que mais
separa um resultado polido de um genérico.

1. **Avalie honestamente contra os 8 pilares.** Percorra cada um e classifique
   **forte / médio / faltando**, sem puxar a brasa para si. O objetivo é saber o
   que ainda falta, não se elogiar.
2. **Corrija em lote, por intenção — não item a item.** Junte os pontos fracos e
   peça um conjunto de melhorias guiado por *como você quer que pareça*: "as
   seções de baixo estão genéricas; não deixe mais cheias, deixe mais caras."
   Descrever a sensação rende mais que microespecificar, e um lote coeso fica
   melhor que muitos ajustes pingados.
3. **Repita a passada de qualidade percebida** nas seções que sobraram chapadas.

> Quando algo quebrar, **insista**: descreva o que esperava e o que aconteceu, e
> deixe o Claude investigar mais fundo. A maioria dos problemas cai em duas ou
> três rodadas quando o contexto é bom.

## Checklist de entrega

- [ ] Os 8 pilares avaliados (forte/médio/faltando) e os fracos corrigidos
- [ ] Identidade = do CLIENTE (cores, logo, tom), não da agência
- [ ] Parece do ramo certo
- [ ] Sistema visual aplicado com consistência (cor, fonte, espaço, ícones)
- [ ] Tipografia com personalidade (sem Inter/Roboto/Arial como título)
- [ ] Hierarquia clara (os tamanhos guiam a leitura)
- [ ] Copy concreta, sem excesso de adjetivos, sem texto de preenchimento
- [ ] Espaços para imagem planejados, com placeholders elegantes onde faltar foto
- [ ] Hero com proposta de valor clara + botão visível
- [ ] Mobile **desenhado** (passada dedicada), não só encolhido
- [ ] Movimento sutil nas seções que ficariam chapadas
- [ ] Funciona no celular (menu, toque ≥44px, sem rolagem horizontal)
- [ ] Botão de WhatsApp / contato funcionando
- [ ] Mapa do Google quando for negócio com endereço
- [ ] Favicon, meta tags e Open Graph
- [ ] Acessibilidade: contraste AA, foco visível, labels, alt
- [ ] `prefers-reduced-motion` respeitado
- [ ] Nenhum dado inventado — o que não foi confirmado está marcado como pendente

## Saída

Arquivos em `clientes/<cliente>/site/`. **Nunca publique sem confirmação.** Ao
terminar, liste o que ficou pendente do cliente (fotos, logo em alta, dados a
validar) e ofereça rodar `/publicar-site`.
