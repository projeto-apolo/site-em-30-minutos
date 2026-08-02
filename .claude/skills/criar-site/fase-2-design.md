# Fase 2 — Playbook de arquitetura + sistema visual

Objetivo: decidir COMO o site é (quantas páginas, o que tem em cada uma) e QUAL é a cara
dele (direção de estilo, paleta, fontes), fechando isso com o operador antes de escrever
qualquer HTML. É o momento mais importante da criação — a decisão daqui vira o site
inteiro, e é a mais cara de refazer depois de construído.

## 1. Uma página ou multipágina?

Decida com o operador, com recomendação:

- **Uma página (long scroll):** landing, negócio simples, objetivo único (captar
  lead/vender um serviço). Publicação mais simples — um `index.html` só.
- **Multipágina:** negócio com vários serviços ou muito conteúdo (ex.: Home, Serviços,
  Sobre, Convênios, Contato).

Monte o **mapa de páginas** (ou de seções, se for uma página só), puxando do `CLIENTE.md`
e adaptado ao objetivo nº1 do site.

## 2. Referências visuais (mostrar é melhor que descrever)

Peça **3 a 5 prints** de sites que o operador ou o cliente curtem — não é pra copiar, é
pra calibrar gosto e direção. Se vierem prints, leia as imagens e extraia: tipo de
layout, densidade, paleta, tratamento de foto, estilo de tipografia, nível de animação.
Sem referência, siga com a proposta própria e as direções abaixo.

## 3. Três direções de estilo (oferecer e deixar escolher)

Antes de fechar a estética, apresente **3 direções distintas**, cada uma com nome, vibe em
1 linha, paleta (com hex) e fontes:

> 1. **Clínico Sereno** — leve e confiável. Azul-petróleo + off-white, muita respiração,
>    tipografia calma. Fontes: Fraunces + Geist.
> 2. **Premium Escuro** — sofisticado. Fundo grafite, acento âmbar, fotos em destaque,
>    movimento discreto. Fontes: ...
> 3. **Fresco Moderno** — jovem e direto. ...

Deixe escolher uma (ou pedir mistura). Isso evita retrabalho na Fase 3.

## 4. Fechar o sistema visual

Invoque a skill **frontend-design** pra calibrar a direção e fugir de cara de template.
Pra intervenção mais pesada de design (paleta/fontes/componente por tipo de negócio),
invoque **ui-ux-pro-max**. A partir da direção escolhida, defina:

- **Ponto de vista:** a ideia central do site em 1 frase (clínica → "precisão, calma,
  confiança"). Intencionalidade vence intensidade.
- **Cor:** paleta da marca **do cliente**, nunca a da agência. 1 dominante + 1 acento
  usado com parcimônia (botões, destaques). Fundo com temperatura sutil, nunca branco
  chapado. Garanta contraste AA (4,5:1 em texto).
  - Ponto de partida por segmento (não é regra): saúde → azul/teal; jurídico e financeiro
    → navy com acento sóbrio; alimentação → tons quentes; tecnologia → escuro com acento
    vivo; beleza e bem-estar → tons suaves. Evite roxo em branco genérico e evite neon.
- **Tipografia:** par display + corpo com personalidade, do Google Fonts.
  **Inter é a fonte "cara de IA" número 1** — se aparecer no resultado, troque (Geist,
  Manrope, Figtree, Sora, Bricolage, Instrument Serif). Idem Roboto e Arial como título.
  Escala consistente (ex.: 12/14/16/20/25/31/39/49).
- **Hierarquia:** o tamanho guia a leitura — nome enorme, detalhe médio, descrição
  pequena. Nunca tamanho aleatório.
- **Espaçamento:** ritmo de 8pt, respiro generoso entre seções.
- **Ícones:** UMA família de SVG de traço consistente. Nunca emoji como ícone.
- **Profundidade:** evite fundo chapado. Com sutileza: textura de pontos, gradiente
  radial suave, linhas finas, sombras coerentes.

Salve tudo isso no `CLIENTE.md`, no campo "Identidade visual → Direção escolhida", com a
justificativa de cada escolha em 1 linha (por que essa paleta combina com o segmento).

## 5. Espaços para imagem e componentes (planejar aqui, não na hora de codar)

- Reserve áreas para: **hero** (ambiente ou composição), **sobre/fachada**, **equipe**
  (retratos), **galeria/serviços**, e fundo de seção quando couber.
- Use primeiro as imagens reais já baixadas (no cadastro do `/novo-cliente` e, se houve,
  na Fase 1). São sempre a melhor opção quando existem.
- **Onde faltar, pesquise banco de imagens antes de qualquer outra saída.** Busque em
  Unsplash/Pexels por termos específicos do segmento e do que a seção precisa (ex.:
  "barbearia vintage cadeira couro", não só "barbearia"). Abra as opções e **confira de
  verdade se combinam** com a direção escolhida (luz, enquadramento, pessoas/ambiente
  compatíveis com o negócio) antes de colar a URL — imagem de banco genérica ou
  descombinada denuncia site de template. Anote no `CLIENTE.md` quais entraram e de
  onde vieram.
- Só se o banco não render nada coerente pro caso (nicho muito específico, ambiente
  incomum), gerar por IA é o próximo caminho: **escreva você mesmo o prompt** — você já
  tem o contexto do projeto (paleta, direção, segmento) e acerta mais rápido que o
  operador tentando descrever. Trate a imagem gerada com o mesmo cuidado de uma real
  (proporção, `alt`, otimização).
- Onde não houver real, de banco nem gerada ainda, planeje um **placeholder elegante e
  marcado** — área com `aspect-ratio` definido, cor da marca, ícone e rótulo do que vai
  ali ("Foto da fachada", "Equipe"). Nunca um retângulo cinza vazio.
- Componentes de efeito premium (hero com scroll, cursor, reveal): se o operador trouxer
  um exemplo do 21st.dev, atenção — a maioria é React. Como o site é HTML puro (ver
  `agencia/stack.md`), **recrie o efeito em HTML/CSS/JS puro**, nunca enfie React num
  arquivo estático.

## ⛔ Checkpoint 2 (obrigatório)

Mostre: mapa de páginas/seções + a direção escolhida + paleta (hex) + fontes. Pergunte se
quer ajustar algo. Só construa depois do "pode ir".
