---
name: instalar
description: >
  Configura a agência na primeira vez que o sistema é aberto. Use quando o
  operador disser "instalar", "configurar", "começar", "vamos começar", "acabei
  de clonar", ou quando os arquivos de `agencia/` ainda estiverem com os
  marcadores de preenchimento. Roda uma vez só — pode ser executada de novo para
  atualizar as respostas.
---

# Skill: Instalar

Primeira coisa que a pessoa faz depois de clonar. É a primeira impressão do
produto inteiro — trate como tal.

Objetivo: em poucos minutos, sair de uma pasta genérica para uma agência que
conhece quem a opera e está pronta para o primeiro cliente.

## Postura

Quem está do outro lado provavelmente nunca usou o VS Code, nunca clonou um
repositório e está com um pé atrás achando que isso é "coisa de programador".

- Fale como gente. Nada de "repositório", "diretório", "dependência".
- Uma pergunta por vez. Nunca despeje um formulário de sete perguntas.
- Elogie o progresso real, sem bajular.
- Se a pessoa não souber responder algo, ofereça um padrão e siga em frente.
  Nada aqui é irreversível — tudo pode ser ajustado depois.

## Passo 1 — Preparar o ambiente

Quem está aqui provavelmente nunca usou nada disso. **Tudo que for preciso
instalar ou configurar acontece agora, uma vez só** — para que na hora de
criar e publicar o primeiro site não apareça nenhuma tela nova, conta nova ou
etapa surpresa no meio do caminho. Resolva nesta ordem, um item de cada vez:

1. **Git** — `git --version`, e `git config user.name`/`user.email`
   configurados. Se faltar, explique em uma linha ("é o que te trouxe a
   estrutura inteira quando você clonou este repositório") e conduza a
   instalação/configuração.

2. **Node.js** — `node -v`. Se faltar, oriente instalar a versão LTS em
   `nodejs.org` (é o que faz o comando de publicação funcionar mais adiante).

3. **Cloudflare** — é onde o site vai ficar no ar. Resolva tudo agora:
   - Pergunte se a pessoa já tem conta. Se não, é gratuita e não pede cartão:
     `dash.cloudflare.com/sign-up`.
   - Rode `npx wrangler login` — abre uma aba do navegador para autorizar.
     Confirme com `npx wrangler whoami` (mostra o e-mail e o ID da conta).
   - **Registre o subdomínio `workers.dev`** — é obrigatório e só existe essa
     janela para fazer uma vez. Abra
     `https://dash.cloudflare.com/<ID da conta>/workers/subdomain` (o ID veio
     do `whoami`) e oriente a pessoa a escolher um nome (sugestão: o nome da
     agência). Sem isso, nenhum site publicado mais tarde vai abrir.

   Explique em uma linha o porquê: "isso é coisa que só se faz uma vez — feito
   agora, na hora de publicar o primeiro site é só um comando."

## Passo 2 — A entrevista

Quatro perguntas. Uma de cada vez, esperando a resposta antes da próxima.

1. **"Como você se chama?"**
   O nome que vai assinar as propostas.

2. **"Sua agência já tem nome? Se ainda não, tudo bem — pode ser o seu nome
   mesmo."**
   Muita gente trava aqui achando que precisa de uma marca pronta. Deixe claro
   que não precisa e que dá para mudar depois.

3. **"Que tipo de negócio você imagina atender primeiro?"**
   Se a pessoa não souber, mostre o que já está pronto em `agencia/nichos/` e
   sugira escolher um. Ter um ramo em mente deixa tudo mais concreto.

4. **"Como você quer soar quando fala com um cliente — mais formal e técnico, ou
   mais próximo e direto?"**
   Uma frase basta. Isso define o tom das propostas e dos textos.

## Passo 3 — Escrever a identidade

Preencha `agencia/identidade.md` com as respostas. Escreva em prosa, não em
formulário — o arquivo vai ser lido pelo Claude a cada tarefa, e texto corrido
carrega mais contexto que campos soltos.

Inclua:

- Nome de quem opera e nome da agência
- Nicho de partida
- Tom de voz, descrito de forma utilizável (não "profissional", mas "direto,
  sem jargão, explica o porquê antes do quê")
- Uma linha de posicionamento: o que essa agência faz e para quem

Deixe explícito no arquivo que ele pode ser editado à mão a qualquer momento.

## Passo 4 — Mostrar o caminho

Feche com um resumo curto do que foi configurado e **um único próximo passo**:

> "Sua agência está de pé. Quando quiser começar, roda `/novo-cliente` — ou dá
> uma olhada em `clientes/exemplo/` pra ver como fica um cliente preenchido."

Duas coisas para mencionar aqui, e só aqui:

- **Renomeie a pasta** para o nome da agência (fechar o VS Code, renomear,
  abrir de novo). A pasta virou o negócio dela.
- O cliente `exemplo/` é fictício e serve de referência. Pode apagar quando
  quiser.

Não liste todas as skills. A pessoa não vai lembrar, e o README já faz isso.
Um próximo passo claro vale mais que um catálogo completo.

## Se rodar de novo

Se `agencia/identidade.md` já estiver preenchido, não recomece do zero. Mostre o
que está lá hoje e pergunte o que mudou. Atualize só o que a pessoa apontar.

Verifique rapidamente o Passo 1 mesmo assim (`npx wrangler whoami` continua
logado? o subdomínio já foi registrado?) — se alguma coisa ainda estiver
faltando, resolva antes de seguir, mesmo numa segunda execução.
