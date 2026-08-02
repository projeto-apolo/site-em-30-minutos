---
name: novo-cliente
description: >
  Cadastra um cliente novo — cria a pasta dele e preenche o briefing que vai
  alimentar a criação do site. Use quando o operador disser "cliente novo",
  "cadastrar cliente", "fechei um projeto", "vou fazer o site da clínica X", ou
  qualquer variação de começar um trabalho para alguém.
---

# Skill: Novo Cliente

O site inteiro nasce daqui. Um briefing raso gera um site genérico — e um site
genérico é o que faz um cliente achar que R$ 200 já foi caro.

Objetivo: sair desta skill com contexto suficiente para o `/criar-site` produzir
algo específico daquele negócio, sem precisar voltar e perguntar.

## Passo 1 — Identificar o cliente

Pergunte o nome do negócio e o ramo. Com isso, crie a pasta:

```
clientes/<nome-em-minusculo-com-hifens>/
├── CLIENTE.md      ← cópia de clientes/_template-cliente/CLIENTE.md
├── site/
└── assets/
```

Copie o template, não escreva do zero. Ele existe para garantir que nenhum campo
importante seja esquecido.

## Passo 2 — Colher antes de perguntar

**Este passo é o que separa 30 minutos de duas horas.**

Se o negócio já tem Instagram, site antigo, perfil no Google ou página no
Facebook, peça o link e **leia antes de entrevistar**. De lá saem, quase sempre:
serviços, endereço, telefone, horário, fotos, tom de voz, e o que o dono já
escolheu destacar sobre o próprio negócio.

Depois de ler, volte com o que você já entendeu e peça só o que faltou:

> "Peguei os serviços e o endereço do Instagram. Me confirma se o horário mudou
> e me diz o que você quer que o site faça — receber contato no WhatsApp,
> mostrar preço, agendar?"

Isso muda a natureza da conversa: em vez de um interrogatório, vira uma
confirmação. O operador parece preparado, e o cliente responde bem menos coisa.

**Aproveite a mesma passada para já baixar imagens reais.** Site atual,
perfil do Google (Google Maps/Google Business) e Instagram costumam ter fotos
de ambiente, fachada, equipe e produto que valem muito mais que qualquer banco
de imagens depois. Baixe as boas — descarte ícone, sprite e logo de terceiro —
e salve em `clientes/<nome>/assets/`. Onde a fonte for um site com muita
página (institucional grande) e a varredura ficar pesada, isso pode esperar a
Fase 1 do `/criar-site`; aqui o objetivo é pegar o que aparece de cara sem
travar o cadastro.

## Passo 3 — O que precisa estar respondido

Não pergunte tudo em sequência. Cubra estes pontos conversando, e pare quando
tiver o suficiente:

**O negócio**
- O que faz, para quem, em qual cidade
- Serviços ou produtos principais (os que ele quer vender, não a lista inteira)
- Há quanto tempo existe, quem são as pessoas

**O que o diferencia**
- Por que alguém escolhe esse negócio e não o concorrente da esquina
- Se a resposta vier vaga ("qualidade", "atendimento"), insista uma vez:
  "qualidade em quê, especificamente?". Um detalhe concreto vale mais que dez
  adjetivos, e é isso que vai virar copy boa.

**O objetivo do site**
- O que precisa acontecer quando alguém entra: chamar no WhatsApp, ligar,
  agendar, ir até o local, pedir orçamento
- **Uma ação principal.** Se vierem três, escolha a que dá dinheiro.

**A cara**
- Logo, cores, fotos — o que já existe (guarde em `assets/`, ver a busca de
  imagens acima)
- Referências: sites que ele acha bonitos ou concorrentes que ele admira
- O que ele **não** quer parecer

**O básico que não pode faltar**
- Telefone/WhatsApp, endereço, horário, redes sociais
- Nome exato como deve aparecer, sem abreviação errada

## Passo 4 — Marcar o que falta

Preencha o `CLIENTE.md` com o que colheu, incluindo o que já foi encontrado
em `assets/` (que imagem é, de onde veio), e **liste explicitamente o que
ficou pendente** na seção de próximos passos — em geral fotos boas e logo em
alta que não apareceram na busca.

Nunca preencha um campo com suposição. Se o horário não foi confirmado, escreva
"a confirmar", não um horário inventado. Um site no ar com informação errada é
um problema do cliente com os clientes dele.

## Passo 5 — Dizer o próximo passo

Feche mostrando o que já dá para fazer:

> "Cliente cadastrado. Dá pra criar o site agora com o que temos — as fotos
> entram depois sem retrabalho. Quer rodar `/criar-site`?"

Se faltar algo que **impede** a criação (não sabe nem o que o negócio vende),
diga qual é a única coisa que falta, e não a lista inteira.

## Cuidados

- Um cliente por pasta. Nunca escreva na pasta de outro (ver Regra Zero no
  `CLAUDE.md`).
- Senha de Instagram, de hospedagem ou de qualquer conta **não entra no
  arquivo**. Anote apenas que o acesso existe e quem o guarda.
