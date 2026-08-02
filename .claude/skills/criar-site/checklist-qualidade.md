# Checklist de qualidade — os 8 elementos do site "de R$ 10 mil"

O que separa um site caro de um de R$ 200. Na Fase 3, avalie o site item por item e marque
cada um como **forte / mediano / faltando** — sem puxar a brasa pra si. Quase sempre imagem,
movimento, mobile e "o invisível" começam medianos, e é aí que mora o polimento.

Os 8 se agrupam em 3 blocos: **bom gosto** (1-4), **conteúdo** (5-6), **qualidade
percebida** (7-8).

## Bom gosto
1. **Ponto de vista** — o site tem uma direção clara, uma ideia central, não é um apanhado
   de referências. Dá pra dizer em 1 frase o que ele comunica.
2. **Tipografia** — fontes com caráter, não genéricas de IA. Sem Inter/Arial/Roboto como
   fonte principal. Par display + corpo bem casado.
3. **Cor** — paleta contida (poucas cores, bem usadas). Moderação passa qualidade; arco-íris
   passa amador. Cor **do cliente**, nunca a do dono da agência.
4. **Hierarquia** — os tamanhos guiam o olho (o que se lê 1º, 2º, 3º). Nada plano, nada do
   mesmo tamanho.

## Conteúdo
5. **Imagens** — nesta ordem: reais do cliente quando dá; senão banco de imagens
   (Unsplash/Pexels) coerente com o segmento; só na falta desse, geradas por IA com
   capricho. Nunca uma imagem que não combina com o negócio. Hero com peso visual.
6. **Texto (copy)** — contido e sensorial. Sem explicar demais, sem excesso de adjetivo, sem
   lorem ipsum. Frases concretas. Vem do `CLIENTE.md`, nada inventado.

## Qualidade percebida
7. **Movimento** — reveal ao rolar, hover states, uma microinteração por seção. Vivo sem ser
   confuso ou irritante. Respeita `prefers-reduced-motion`. Transições de 200-400ms.
8. **Mobile pensado pra mobile** — não é o desktop encolhido. Revisão dedicada: o que
   esconder, compactar, redimensionar. Menu hambúrguer funcional, alvos ≥ 44px, zero rolagem
   horizontal. Testado em 375px de largura.
   **+ O invisível** — a sensação de rápido e acabado: fonte com `preconnect`, imagem com
   `lazy` + `alt`, ícone em SVG, HTML semântico, `<title>`/meta/Open Graph, conteúdo visível
   com JavaScript desligado, nada quebrado em 375/768/1440px.

## Régua de conteúdo (não esquecer)
- [ ] Textos e dados vêm do `CLIENTE.md`, nada inventado.
- [ ] Placeholders de imagem que faltam estão marcados pro cliente trocar.
- [ ] Telefone, WhatsApp, endereço e horário conferem com o `CLIENTE.md`.
- [ ] O objetivo nº1 do site (a ação que ele precisa gerar) está no centro da página.
