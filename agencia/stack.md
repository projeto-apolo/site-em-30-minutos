# Tecnologia padrão

> As ferramentas usadas nas entregas. Manter o padrão é o que permite reaproveitar
> aprendizado de um projeto para o outro — e é o que torna o segundo site muito
> mais rápido que o primeiro.

## Sites

**Página única ou site institucional simples** → HTML + CSS + JavaScript puro.

É o padrão para negócio local. Rápido de fazer, rápido de carregar, fácil de
publicar e fácil de mexer depois. A grande maioria dos clientes é bem servida
por aqui.

**Site com mais interatividade** → React + Vite + Tailwind CSS.

Só quando houver motivo real: muitas seções dinâmicas, área de conteúdo que
muda, filtros, catálogo grande. Complexidade cobra preço na manutenção.

> Na dúvida entre os dois, escolha o primeiro.

## Publicação

- **GitHub** guarda os arquivos e o histórico
- **Vercel** publica e hospeda (plano gratuito atende negócio local com folga)

Um repositório **privado por cliente**. Publicação conectada ao repositório, para
que cada alteração salva vá ao ar sozinha.

Domínio próprio é sempre pago e sempre decisão do cliente — ver
`.claude/skills/publicar-site/`.

## Ferramentas de trabalho

- **VS Code** com a extensão do Claude
- **Git** configurado com nome e e-mail

## Imagens

- Foto real do cliente é sempre o ideal
- Enquanto não chega, imagem gerada por IA é caminho válido para hero e seções
- Onde não houver nem uma nem outra, placeholder marcado e elegante — nunca
  retângulo cinza vazio
- Formatos WebP ou AVIF para foto real; sempre com `alt`

---

> Atualize este arquivo conforme sua forma de trabalhar se firmar. Se você mudar
> de ferramenta, é aqui que se registra.
