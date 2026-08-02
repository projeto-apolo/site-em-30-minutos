---
name: publicar-site
description: >
  Coloca o site do cliente no ar via Cloudflare Pages e devolve o link público.
  Use quando o operador disser "publicar", "colocar no ar", "subir o site",
  "gerar o link", "mandar pro cliente ver". Para antes de qualquer coisa que
  envolva domínio pago ou dado de cartão — essa etapa é sempre do operador.
---

# Skill: Publicar Site

É o momento em que o trabalho vira algo que existe no mundo. Também é onde mais
gente trava — porque envolve criar conta e ver tela que nunca viu.

Conduza com calma. Um passo por vez, confirmando antes de seguir.

## Antes de publicar

1. Confirme qual cliente e que o site em `clientes/<cliente>/site/` está pronto.
2. **Peça autorização explícita.** Publicar é um ato público. Mostre o que vai
   ao ar e espere o "pode subir".
3. Rode uma última conferência: links funcionando, botão de WhatsApp com o
   número certo, nenhum texto de preenchimento sobrando, nada inventado.

## O caminho padrão: direto do arquivo pra Cloudflare

**Sem GitHub, sem Vercel.** O site sobe direto da pasta local, com uma conta só
(gratuita), criada e configurada **uma vez, no `/instalar`** — login e
subdomínio já devem estar prontos antes de chegar aqui.

O motivo de ser assim: **um passo a menos** para quem nunca programou. Não é
preciso entender o que é um repositório nem conectar duas contas diferentes —
é um comando, um link.

**A troca:** sem repositório, cada correção futura no site exige rodar o envio
de novo (não é automático como seria com um repositório conectado). Para o
ritmo deste método — publicar rápido e ajustar pontualmente — isso é aceitável;
avise o operador dessa troca quando publicar pela primeira vez.

### Passo 1 — Conferir que o ambiente está pronto

Isso já devia ter sido resolvido no `/instalar`. Confirme rápido com
`npx wrangler whoami` — se aparecer o e-mail da conta, está tudo certo. Se
disser "not authenticated" ou o subdomínio `workers.dev` nunca foi registrado,
**pare e rode o `/instalar` de novo** antes de publicar qualquer coisa — é mais
rápido resolver ali, de forma guiada, do que no meio da publicação.

### Passo 2 — Publicar

Rode o envio apontando para a pasta do site do cliente, com um nome de projeto
único (o nome vira parte do link):

```bash
npx wrangler deploy clientes/<cliente>/site --project-name <cliente-slug>
```

- **Um projeto por cliente.** Nunca reaproveite o nome de projeto de um
  cliente para outro (ver Regra Zero no `CLAUDE.md`).
- `<cliente-slug>` é o mesmo nome de pasta do cliente, em minúsculo e com
  hífen — mantém o link legível e fácil de rastrear.
- Se o terminal mostrar um aviso de "Cloudflare Pages" ou sugerir outro
  comando, ignore — `wrangler deploy` já é o caminho direto e correto, sem
  passo a mais.

Se for a primeira vez da pessoa, explique em uma linha o que está acontecendo:
"estou mandando os arquivos do site direto para a nuvem da Cloudflare, que já
devolve o link publicado".

O link sai no formato `<cliente-slug>.<subdomínio-da-agência>.workers.dev`
(o subdomínio é o que foi escolhido no `/instalar`). **Esse é o link para
mandar ao cliente ver.**

**No primeiro deploy de um projeto novo, o link pode demorar de 1 a 5 minutos
para ficar acessível** (propagação). Se abrir e der erro na hora, não é
sinal de que algo quebrou — espere um pouco e tente de novo antes de mexer em
qualquer coisa.

### Passo 3 — Testar de verdade

Antes de mandar para o cliente, abra o link e confira:

- Todas as páginas carregam
- O menu funciona
- Os botões de WhatsApp e telefone abrem certo
- **Abra no celular.** É onde o cliente vai olhar primeiro.
- As imagens aparecem (as que já existem)

Se algo estiver quebrado, conserte e rode o envio de novo antes de mostrar. A
primeira impressão do cliente com o link acontece uma vez só.

### Passo 3b — Medir a velocidade

Com o link no ar, jogue a URL no **`pagespeed.web.dev`** e olhe a **aba Mobile**.

**A meta é 90 ou mais em Performance.** Abaixo disso, o próprio relatório lista o
que corrigir — e quase sempre é imagem grande demais. Corrija, rode o envio de
novo, meça de novo.

Guarde o resultado: **essa captura de tela é material de venda.** Rodar o teste
no site do concorrente do seu cliente e mostrar os dois lado a lado é o argumento
mais fácil de provar que existe nesse serviço. Vale para fechar o próximo
cliente, e vale para justificar o preço deste.

### Passo 4 — Registrar

Anote no `CLIENTE.md`: o link publicado, o nome do projeto na Cloudflare (para
saber qual comando rodar numa próxima atualização), a data, e o que ficou
pendente.

### Atualizando o site depois de publicado

Toda alteração (novo texto, ajuste de imagem, correção) precisa do mesmo
comando de novo, com o **mesmo** `--project-name`:

```bash
npx wrangler deploy clientes/<cliente>/site --project-name <cliente-slug>
```

O link não muda — só o conteúdo é atualizado.

## Domínio próprio

Se o cliente quer `nomedaempresa.com.br` em vez do link `.workers.dev`:

- **Se ele já tem domínio:** é uma configuração de apontamento, feita direto no
  painel do projeto na Cloudflare (Custom domains). Dá para conduzir, mas exige
  acesso ao painel onde o domínio foi registrado — normalmente é o próprio
  cliente ou o contador dele que tem.
- **Se ele não tem:** domínio é **pago** (algo em torno de R$ 40 a R$ 120 por
  ano, no Brasil). **Não compre nada em nome do cliente.** Explique o custo,
  deixe que ele decida e, se possível, que ele registre em nome dele — domínio
  no nome do cliente evita uma dor de cabeça enorme se um dia vocês se
  separarem.

**Pare antes de qualquer tela de pagamento.** Cartão e compra são sempre do
operador ou do cliente, nunca automatizados aqui.

## Quando é só uma demonstração

Se o site é uma **demo descartável** — aquela que você monta para mostrar a um
prospect antes de fechar — publique do mesmo jeito, só que sem se preocupar em
manter o projeto depois. Trate como material de venda, sabendo que talvez você
suba por cima dele mais tarde.

## Se der errado

Erro na publicação quase sempre é uma destas três coisas:

- **Caminho errado da pasta** — o comando está apontando para o lugar errado
  (confira se está na raiz do workspace, não dentro da pasta do cliente).
- **Arquivo principal com nome errado** — a página inicial precisa se chamar
  `index.html`.
- **Sessão da Cloudflare expirada** — rode `npx wrangler login` de novo.
- **Link não abre logo depois de publicar** — normal no primeiro deploy de um
  projeto (propagação); espere 1-5 minutos e teste de novo antes de mexer em
  qualquer coisa.

Diga qual é, em português, e resolva. Não mostre a mensagem de erro crua para
alguém que não programa: traduza o que aconteceu e o que vai fazer a respeito.
