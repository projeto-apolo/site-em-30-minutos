---
name: publicar-site
description: >
  Coloca o site do cliente no ar via Vercel e devolve o link público. Use
  quando o operador disser "publicar", "colocar no ar", "subir o site",
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

## O caminho padrão: direto do arquivo pra Vercel

**Sem repositório por cliente.** O site sobe direto da pasta local, com uma
conta só (gratuita), criada e configurada **uma vez, no `/instalar`** — login e
token de API já devem estar prontos antes de chegar aqui.

O motivo de ser assim: **um passo a menos** para quem nunca programou. Não é
preciso criar um repositório novo para cada cliente nem sair conectando
GitHub a cada projeto — é um comando, um link.

**A troca:** sem repositório conectado ao projeto, cada correção futura no
site exige rodar o envio de novo (não é automático como seria com um push no
GitHub). Para o ritmo deste método — publicar rápido e ajustar pontualmente —
isso é aceitável; avise o operador dessa troca quando publicar pela primeira
vez.

### Passo 1 — Conferir que o ambiente está pronto

Isso já devia ter sido resolvido no `/instalar`. Confirme rápido com
`npx vercel whoami` — se aparecer o nome da conta, está tudo certo. Se disser
que não está autenticado, **pare e rode o `/instalar` de novo** antes de
publicar qualquer coisa — é mais rápido resolver ali, de forma guiada, do que
no meio da publicação.

### Passo 2 — Publicar

**Primeira publicação deste cliente** — vincula a pasta a um projeto novo, com
nome único, e já publica:

```bash
cd clientes/<cliente>/site
npx vercel link --yes --project <cliente-slug>
npx vercel deploy --prod --yes
cd -
```

- **Um projeto por cliente.** `<cliente-slug>` é o mesmo nome de pasta do
  cliente, em minúsculo e com hífen — nunca reaproveite o nome de projeto de
  um cliente para outro (ver Regra Zero no `CLAUDE.md`).
- O `vercel link` cria uma pasta `.vercel/` dentro do site do cliente, com a
  ligação ao projeto — é o que faz as próximas publicações desse mesmo cliente
  caírem sempre no mesmo lugar. Essa pasta já está no `.gitignore`.

Se for a primeira vez da pessoa, explique em uma linha o que está acontecendo:
"estou mandando os arquivos do site direto para a nuvem da Vercel, que já
devolve o link publicado".

O link sai no formato `<cliente-slug>.vercel.app` (ou parecido — a Vercel pode
ajustar o nome se já existir um projeto igual em outra conta). **Esse é o link
para mandar ao cliente ver.**

O link da Vercel costuma ficar acessível em poucos segundos. Se abrir e der
erro na hora, espere um pouco e tente de novo antes de mexer em qualquer
coisa — não é sinal de que algo quebrou.

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

Anote no `CLIENTE.md`: o link publicado, o nome do projeto na Vercel (para
saber qual comando rodar numa próxima atualização), a data, e o que ficou
pendente.

### Atualizando o site depois de publicado

Toda alteração (novo texto, ajuste de imagem, correção) roda o mesmo comando
de publicação — como a pasta já está vinculada (`.vercel/` já existe),
**não precisa rodar `vercel link` de novo**, só:

```bash
cd clientes/<cliente>/site
npx vercel deploy --prod --yes
cd -
```

O link não muda — só o conteúdo é atualizado.

## Domínio próprio

Se o cliente quer `nomedaempresa.com.br` em vez do link `.vercel.app`:

- **Se ele já tem domínio:** é uma configuração de apontamento, feita direto no
  painel do projeto na Vercel (Settings → Domains). Dá para conduzir, mas exige
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
- **Sessão da Vercel expirada** — rode `npx vercel login` de novo.
- **Link não abre logo depois de publicar** — raro na Vercel, mas pode
  acontecer no primeiro deploy de um projeto; espere um pouco e teste de novo
  antes de mexer em qualquer coisa.

Diga qual é, em português, e resolva. Não mostre a mensagem de erro crua para
alguém que não programa: traduza o que aconteceu e o que vai fazer a respeito.
