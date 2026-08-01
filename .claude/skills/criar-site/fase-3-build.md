# Fase 3 — Playbook de construção

Objetivo: construir o site aplicando o que foi decidido na Fase 2, e polir até parecer
caro de verdade. Não é montar e já mostrar — é montar, se autoavaliar contra o checklist,
corrigir em lote e polir seção a seção. Essa camada de polimento é o que separa "site de
IA genérico" de "caramba, esse site é top".

## 1. Montar a estrutura

- **Sempre HTML + CSS + JavaScript puro** (ver `agencia/stack.md`). Um `index.html`, um
  `styles.css`, um `main.js`. Sem framework, sem build, sem biblioteca externa.
  - Não pergunte se deve usar React, Tailwind ou qualquer outra coisa — a resposta é não.
    Site de negócio local nunca precisou disso.
  - **Efeito que você viu por aí é ideia, não código.** Se achar uma animação boa numa
    biblioteca, recrie com as poucas linhas que ela exige. Colar dependência troca
    segundos de trabalho por pontos de desempenho e um ponto de falha permanente.
- **Multipágina:** um HTML por página (`index.html`, `servicos.html`...), com
  header/rodapé/CSS/JS compartilhados e navegação real entre elas. **Uma página:**
  `index.html` único.
- Gere os arquivos em `clientes/<cliente>/site/`.
- Defina os tokens da marca em `:root` (cores, fontes, espaçamento, raio, sombra) — uma
  única fonte da verdade, nunca cor solta espalhada pelo código.
- Seções que vendem, adaptadas ao objetivo nº1: hero forte com proposta de valor + CTA
  claro; prova social; serviços/produtos; diferenciais; sobre; depoimentos; CTA final;
  rodapé com contato. CTA principal repetido em pontos estratégicos. WhatsApp/telefone
  sempre à mão.
- **Comece pelo texto do hero, não pelo visual.** Erro comum: montar a imagem primeiro e
  depois não achar um tratamento de texto que case. Feche primeiro o layout de texto
  (headline, hierarquia, copy) e construa o visual ao redor dele.

## 2. O conteúdo nunca depende do JavaScript pra aparecer

Este é o erro mais fácil de cometer e o mais caro: esconder tudo com `opacity: 0` no CSS e
deixar o JavaScript revelar ao rolar. Fica lindo — até o JavaScript falhar, demorar numa
rede ruim ou ser bloqueado. Aí o visitante recebe **uma página em branco**, e ninguém
fica sabendo.

O jeito certo é inverter: o site nasce visível, e o JavaScript **liga** a animação. Na
prática, o JS marca a página como primeira instrução (ex.:
`document.documentElement.classList.add('anim')`), e o CSS só esconde dentro de `.anim`.
Sem JavaScript, tudo aparece normalmente — só sem o efeito.

**Teste sempre com o JavaScript desligado** antes de considerar pronto. Se a página ficar
vazia, está errado, por mais bonita que esteja com ele ligado.

## 3. Desempenho — requisito, não bônus

Meta: **90 ou mais em Performance no PageSpeed Insights, aba Mobile**
(`pagespeed.web.dev`). Site lento perde visitante e posição no Google — e é o argumento
de venda mais fácil de provar: abrir o teste com o site do concorrente ao lado convence
mais que qualquer apresentação. Aplique **enquanto constrói**, não depois:

- **Imagem é onde os pontos se perdem.** WebP ou AVIF, redimensionada antes de entrar. A
  imagem do topo leva `fetchpriority="high"` e **nunca** `loading="lazy"`. Todas as
  demais levam `loading="lazy"`. Sempre com `width`/`height` ou `aspect-ratio`.
- **Fonte:** no máximo duas famílias, só os pesos usados, com `preconnect` e
  `display=swap`.
- **Zero dependência externa.**
- **Nada de vídeo com reprodução automática no topo, e nada de 3D.**
- **Movimento:** discreto, em CSS, respeitando `prefers-reduced-motion`, nunca travando a
  rolagem.

Se vier abaixo de 90, o próprio relatório do PageSpeed diz o que corrigir — quase sempre é
imagem.

**Técnica do elemento-âncora:** pegue o elemento visual grande do topo e reaproveite-o na
transição para a próxima seção — ele se move ou escala conforme a rolagem e "costura" as
duas. Dá coesão e sensação premium, com custo quase zero de desempenho.

## 4. Autoavaliar contra o checklist (honesto)

Abra `checklist-qualidade.md` (os 8 elementos) e avalie de verdade, item por item, como
**forte / mediano / faltando**. Seja honesto: quase sempre imagem, movimento, mobile e "o
invisível" começam medianos — é normal, serve pra saber o que ainda falta.

## 5. Corrigir em LOTE (por intenção, não item a item)

Nos itens medianos, não corrija um de cada vez. Proponha um lote de melhorias guiado por
*como quer que pareça*, não por microdetalhe: "as seções de baixo estão genéricas; deixar
mais caras, não mais cheias". Traduza isso num conjunto coeso de mudanças (ex.: fio fino
animado entre seções, reveal palavra a palavra dos títulos, destaque no CTA) e implemente
junto. Menos idas e vindas, resultado mais coeso.

## 6. Polir SEÇÃO A SEÇÃO (a camada que faz parecer caro)

Passe por cada seção e ache as que ficaram "sem graça, paradas" — sempre tem alguma. Pra
cada uma, acrescente **uma** microinteração ou efeito de cursor, sutil:

- reveal ao rolar (IntersectionObserver) com stagger,
- hover state que surpreende,
- efeito que reage ao cursor (parallax leve, brilho/halo com leve atraso, tilt suave em
  card).

Regra do vídeo: se ficar óbvio demais, refaça "mais sutil, mais refinado". Um efeito por
seção basta. Respeite `prefers-reduced-motion`.

## 7. Copy contida e sensorial

Reescreva texto que soa de IA. IA por padrão explica demais, enche de adjetivo, tenta
impressionar. O caro é o contido: frases curtas, sensoriais, concretas ("Seis pratos, uma
fogueira" vale mais que um parágrafo elogiando a comida). A skill **frontend-design**
ajuda nesse tom. Nada de lorem ipsum. Texto vem do `CLIENTE.md`, nada inventado.

## 8. Passe mobile DEDICADO (não é só responsivo)

Responsivo (encolhe) não é o mesmo que pensado pra celular — e a maioria dos acessos é
mobile. Faça uma revisão só do celular decidindo, por seção, o que **esconder**,
**compactar** e **redimensionar** (menu vira hambúrguer e funciona, espaçamento mais
justo, botões menores, hero recomposto, alvos de toque ≥ 44px, zero rolagem horizontal).
Teste mentalmente em 375 / 768 / 1024 / 1440.

## 9. Técnico e SEO

- Fontes via Google Fonts com `preconnect`. Ícones em SVG inline. HTML semântico (header,
  main, section, footer).
- `<title>`, meta description, Open Graph, `lang`, favicon, `alt` em toda imagem.
- Acessibilidade: contraste AA, foco visível (`:focus-visible`), labels reais em
  formulário, `aria-label` em botão só com ícone, hierarquia de títulos correta.

## 10. Validar antes de mostrar (sem queimar token)

**Não use ferramenta de navegador pra tirar e LER screenshot de volta pra conversa.** Ler
uma imagem de página inteira pra dentro do contexto é o que mais gasta token, e quem bate
o olho no visual de verdade é o operador, no navegador dele — é o próprio Checkpoint 3. A
validação aqui é barata:

1. **Revisão do código** (você escreveu, você confere): passe o olho no HTML/CSS contra o
   `checklist-qualidade.md`. Confira manualmente: media queries de 375/768/1440, `alt` e
   `loading="lazy"` nas imagens, meta/title/OG, nav mobile, alvos de toque, sem
   `overflow-x`.
2. Se um print for mesmo necessário pra confirmar algo pontual, salve o arquivo e passe o
   **caminho** para o operador abrir — não leia o PNG de volta pra conversa.
3. Confira que as imagens de banco combinam de verdade com o negócio — decisão tomada na
   hora de escolher a imagem, não depois olhando print.

Limpe arquivos temporários (servidor local, prints soltos) da pasta do projeto ao final.

## ⛔ Checkpoint 3 (entrega)

Abra o site pro operador (caminho do arquivo). Pergunte o que ajustar e itere até
aprovar. Aí sim ofereça publicar (`/publicar-site`) e atualize o `CLIENTE.md` com o que
foi decidido.
