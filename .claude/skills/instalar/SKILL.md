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

## Passo 1 — Conferir o ambiente

Antes de perguntar qualquer coisa, verifique em silêncio o que já está pronto:

- `git --version` — o Git está instalado?
- `git config user.name` e `git config user.email` — já estão configurados?

Se o Git não estiver instalado ou configurado, resolva **antes** de continuar:
explique em uma linha para que serve ("é o que guarda o histórico do seu
trabalho e permite publicar o site depois") e conduza a instalação/configuração.

Não peça conta de GitHub nem de Vercel agora. Isso só é necessário na hora de
publicar, e a skill `/publicar-site` cuida disso. Pedir cadastro antes da hora é
a forma mais rápida de perder alguém no começo.

## Passo 2 — A entrevista

Cinco perguntas. Uma de cada vez, esperando a resposta antes da próxima.

1. **"Como você se chama?"**
   O nome que vai assinar as propostas.

2. **"Sua agência já tem nome? Se ainda não, tudo bem — pode ser o seu nome
   mesmo."**
   Muita gente trava aqui achando que precisa de uma marca pronta. Deixe claro
   que não precisa e que dá para mudar depois.

3. **"Em que cidade ou região você pretende atender?"**
   Importa de verdade: negócio local é vendido por proximidade, e o site precisa
   falar da cidade certa.

4. **"Que tipo de negócio você imagina atender primeiro?"**
   Se a pessoa não souber, mostre o que já está pronto em `agencia/nichos/` e
   sugira escolher um. Ter um ramo em mente deixa tudo mais concreto.

5. **"Como você quer soar quando fala com um cliente — mais formal e técnico, ou
   mais próximo e direto?"**
   Uma frase basta. Isso define o tom das propostas e dos textos.

## Passo 3 — Escrever a identidade

Preencha `agencia/identidade.md` com as respostas. Escreva em prosa, não em
formulário — o arquivo vai ser lido pelo Claude a cada tarefa, e texto corrido
carrega mais contexto que campos soltos.

Inclua:

- Nome de quem opera e nome da agência
- Cidade/região de atuação
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
