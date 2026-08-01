---
name: criar-site
description: >
  Cria o site ou landing page de um cliente, do zero, no padrão "site de R$ 10 mil".
  Roda em 3 fases com CHECKPOINT obrigatório em cada uma (coletar dados, definir
  arquitetura + sistema visual, construir). Use quando a tarefa for "criar site",
  "fazer landing page", "montar a página", "site do cliente X" ou variações.
---

# Skill: Criar Site

Objetivo: entregar sites que pareçam **feitos sob medida** — nunca "template de agência
genérico". Cada site deve transmitir a essência daquele negócio: uma clínica parece
clínica, um restaurante parece restaurante.

É aqui que o método se prova. Um site que parece caro é o que sustenta o preço cobrado,
gera indicação e vira portfólio. Um site genérico faz o cliente perguntar por que não
usou um construtor gratuito.

**Esta skill é a ORQUESTRADORA.** Ela conduz 3 fases. Cada fase tem um playbook próprio
(arquivo nesta pasta) que você deve ler e seguir ao entrar nela, e termina num
**checkpoint obrigatório**: você mostra o resultado pro operador e SÓ AVANÇA quando ele
confirmar. Nada de rodar as 3 fases direto sem parar.

- Fase 1 → `fase-1-coleta.md` — só se o cliente já tem site atual a substituir
- Fase 2 → `fase-2-design.md` — arquitetura de páginas + sistema visual + referências
- Fase 3 → `fase-3-build.md` — construir, autoavaliar, polir seção a seção, passe mobile
- Régua de qualidade → `checklist-qualidade.md` — os 8 elementos do site "de R$ 10 mil"

## A régua: os 8 pilares de um site "caro"

O que separa um site de R$ 10 mil de um de R$ 200 são **8 pilares**, em três grupos. Use
como régua do início ao fim — toda decisão serve a um deles. Detalhados em
`checklist-qualidade.md`: ponto de vista, tipografia, cor e hierarquia (bom gosto);
imagem e copy (substância); mobile desenhado e "o invisível" (qualidade percebida).

## Regra de ouro — a identidade é DO CLIENTE

**Toda entrega segue a identidade visual do cliente, não a da agência.** Extraia paleta,
logo e tom da marca dele (do site atual, da logo, das fotos, do `CLIENTE.md`).

A identidade da agência (`agencia/identidade.md`) serve só para as peças da própria
agência — propostas, apresentações. Nunca é imposta na entrega do cliente.

Se o cliente não tem identidade definida, proponha uma coerente com o segmento dele.
Comece pelo arquivo do ramo em `agencia/nichos/`, se houver um que sirva.

**Site sempre novo do zero.** Se o cliente já tem site, ele é só FONTE DE INFORMAÇÃO e de
IMAGENS, além de referência do que evitar. Nunca clonar nem reaproveitar a estrutura
antiga — isso herda os defeitos dela.

**Não inventar dado do cliente.** Se não achou, marque como lacuna e pergunte no
checkpoint.

**Tom:** o que estiver combinado em `agencia/identidade.md`. Fazer e mostrar, parar nos
checkpoints, juntar as dúvidas num bloco só.

## Antes de começar (obrigatório)

1. Confirme **qual cliente** e leia `clientes/<cliente>/CLIENTE.md`.
2. Leia `agencia/stack.md` e, se existir, `agencia/nichos/<ramo>.md`.
3. Veja o que já tem em `clientes/<cliente>/assets/` (logo, fotos, textos).

Com isso lido, siga para a Fase 1 (se houver site atual do cliente) ou direto para a
Fase 2.

## ⛔ Checkpoint 1 — depois de coletar (ver `fase-1-coleta.md`)
Resumo dos dados achados e lacunas. Só avança com o "confere".

## ⛔ Checkpoint 2 — depois de desenhar (ver `fase-2-design.md`)
Mapa de páginas + direção visual escolhida + paleta e fontes. Só constrói com o "pode ir".

## ⛔ Checkpoint 3 — na entrega (ver `fase-3-build.md`)
Site aberto pro operador. Itera até aprovar, aí oferece `/publicar-site`.

## Reentrar numa fase só

Se pedirem pra refazer só uma parte ("muda o design", "acha mais imagens", "reescreve a
copy"), reentre SÓ naquela fase usando os artefatos já salvos no `CLIENTE.md` e em
`assets/`, sem refazer o resto.

## Saída

Arquivos em `clientes/<cliente>/site/`. **Nunca publique sem confirmação.** Ao terminar,
liste o que ficou pendente do cliente (fotos, logo em alta, dados a validar) e ofereça
rodar `/publicar-site`.
