# Tecnologia padrão

> As ferramentas usadas nas entregas. Manter o padrão é o que permite reaproveitar
> aprendizado de um projeto para o outro — e é o que torna o segundo site muito
> mais rápido que o primeiro.

## Sites — sempre HTML

**Todo site é HTML + CSS + JavaScript puro.** Sem exceção, sem framework, sem
build.

Não é limitação, é escolha. Um site em HTML puro:

- **abre mais rápido** que qualquer alternativa, e velocidade é o argumento de
  venda mais fácil de provar na frente do cliente;
- **não quebra sozinho** — não tem dependência que desatualiza, build que falha
  nem versão de biblioteca que conflita;
- **publica direto**, sem etapa de compilação;
- **é editável daqui a dois anos**, por você ou por qualquer pessoa.

Um site de negócio local nunca precisou de mais que isso. O que faz esse site
parecer caro é design, texto e foto — não a tecnologia por trás.

### Sem bibliotecas externas

Nada de jQuery, biblioteca de animação, framework de CSS ou script vindo de CDN.
Cada arquivo externo é uma requisição a mais, um ponto de falha a mais e alguns
pontos a menos no teste de velocidade.

Se você precisa de um efeito, escreva as poucas linhas que ele exige. É quase
sempre menos trabalho do que integrar uma biblioteca — e infinitamente mais leve.

**Exceção única:** a fonte. Ver abaixo.

## Desempenho — a meta é 90+

Todo site entregue deve marcar **90 ou mais em Performance no PageSpeed
Insights, na aba Mobile** (`pagespeed.web.dev`). É a aba que conta: é assim que
o Google avalia, e é de celular que o cliente do seu cliente acessa.

As regras que garantem isso:

**Fonte**
- No máximo **duas famílias** e só os pesos realmente usados.
- Google Fonts com `preconnect` e `display=swap`. Se quiser os últimos pontos,
  baixe os arquivos `.woff2` e sirva junto com o site — elimina a requisição
  externa.

**Imagem** — é onde 90% dos pontos se perdem
- Sempre **WebP ou AVIF**, nunca PNG ou JPG grande direto da câmera.
- Redimensione antes de subir. Ninguém precisa de 4000px de largura.
- A imagem do topo (a primeira que aparece) leva `fetchpriority="high"` e
  **nunca** `loading="lazy"` — ela é o que o teste mede como carregamento
  principal.
- Todas as outras levam `loading="lazy"`.
- Sempre com `width`/`height` ou `aspect-ratio`, para a página não pular
  enquanto carrega.

**Código**
- Um `styles.css` e um `main.js`, só.
- Conteúdo visível sem JavaScript (ver a skill `criar-site`).
- Nada de vídeo com reprodução automática no topo, nada de 3D pesado.

**Como testar:** publique, jogue a URL no `pagespeed.web.dev`, aba Mobile. Se
vier abaixo de 90, o próprio relatório diz o que corrigir — e quase sempre é
imagem.

## Publicação

- **Vercel**, direto da pasta do site (`npx vercel deploy --prod`). Sem
  repositório por cliente — uma conta gratuita só, com login feito **de uma
  vez no `/instalar`** e reaproveitada em todos os clientes.

Um **projeto por cliente**. Cada atualização do site exige rodar o comando de
envio de novo (não há repositório conectado nem deploy automático) — ver
`.claude/skills/publicar-site/`. O link sai no formato
`<cliente-slug>.vercel.app`, e costuma ficar acessível em poucos segundos.

Domínio próprio é sempre pago e sempre decisão do cliente — ver
`.claude/skills/publicar-site/`.

## Ferramentas de trabalho

- **VS Code** com a extensão do Claude
- **Node.js** instalado (o `npx vercel` do passo de publicação depende dele)

## Imagens

Ordem de prioridade (ver `.claude/skills/criar-site/fase-2-design.md`):

1. Foto real do cliente é sempre o ideal.
2. Faltando, pesquisar banco de imagens (Unsplash/Pexels) com termo específico
   do segmento — e conferir de verdade que combina antes de usar.
3. Se o banco não render nada coerente, imagem gerada por IA é caminho válido
   para hero e seções.
4. Onde não houver nenhuma das três, placeholder marcado e elegante — nunca
   retângulo cinza vazio.

Formatos WebP ou AVIF para foto real; sempre com `alt`.

---

> Atualize este arquivo conforme sua forma de trabalhar se firmar. Se você mudar
> de ferramenta, é aqui que se registra.
