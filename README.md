# Site em 30 Minutos

> A estrutura que transforma as informações de um negócio em um site profissional
> publicado — usando o Claude, sem escrever uma linha de código.

Você acabou de receber sua **agência**. Ela vem vazia de propósito: em alguns
minutos você responde algumas perguntas, ela passa a te conhecer, e a partir daí
cada site novo é só repetir o mesmo caminho.

**Prepare sua agência → organize o cliente → crie com o Claude → publique.**

---

## Ligando o sistema

Você precisa de duas coisas instaladas antes: o **VS Code** e a **extensão do
Claude** dentro dele. Por baixo, o método também usa o **Git** (traz esta
estrutura) e o **Node** (publica seus sites) — mas você não precisa se preocupar
com nenhum dos dois: o próprio Claude verifica e instala o que faltar. A Aula
01.2 do Módulo 01 mostra tudo isso.

**Você não precisa de conta no GitHub**, e **não vai digitar comando nenhum.**
Quem traz a estrutura é o Claude — você só pede, em português.

### 1. Escolher onde a agência vai morar

Abra o VS Code e, em **File → Open Folder**, escolha a pasta onde a agência vai
ficar guardada: Documentos, Área de Trabalho, onde preferir. É dentro dela que a
estrutura vai aparecer.

### 2. Pedir ao Claude para trazer a estrutura

Abra a extensão do Claude na lateral e peça, com suas palavras:

```
Clone o repositório https://github.com/projeto-apolo/site-em-30-minutos
aqui nesta pasta.
```

Autorize quando ele pedir permissão para executar. Ele avisa quando terminar.

*Se ele disser que falta o **Git** — o programa que faz o download —, peça que
ele te oriente a instalar, e repita o pedido acima.*

### 3. Abrir a pasta nova — o passo que não pode ser pulado

A estrutura chegou como uma **pasta nova** dentro da que você abriu. Vá em
**File → Open Folder** e escolha essa pasta nova.

**Por que isso importa:** as skills (`/instalar`, `/novo-cliente`, `/criar-site`,
`/publicar-site`) moram dentro dela. O Claude só enxerga essas skills quando ela
está aberta como projeto — não basta ela existir no computador. **Se o Claude já
estava aberto, feche e abra de novo**, do contrário os comandos simplesmente não
vão existir.

### 4. Confirmar que as skills apareceram

Com a pasta nova aberta, abra o Claude e digite `/`.

Se `/instalar` aparecer na lista, está tudo certo. **Rode `/instalar`.**

Se **não** aparecer, é sempre a mesma causa: a pasta aberta não é a pasta nova,
ou o Claude foi aberto antes dela. Feche o Claude, confirme que a janela está na
pasta certa, e abra de novo.

---

### Depois do `/instalar`

Renomeie a pasta `site-em-30-minutos/` para o nome da **sua** agência. Feche o
VS Code, renomeie no Finder/Explorador, abra de novo.

Não é firula. A pasta deixou de ser o meu template e virou o seu negócio.

O `/instalar` roda **uma vez só**. Depois disso é só usar.

---

## O que você tem em mãos

**O caminho de um site** — na ordem em que você vai usar

| Skill | O que faz |
|---|---|
| `/instalar` | Configura a agência com o seu nome, seu tom e seu jeito. Roda uma vez. |
| `/novo-cliente` | Entrevista você sobre o cliente e monta a pasta dele com tudo organizado. |
| `/criar-site` | Transforma o briefing em um site profissional de verdade. O coração do método. |
| `/publicar-site` | Coloca o site no ar e te devolve o link para mandar ao cliente. |

**Na hora de vender**

| Skill | O que faz |
|---|---|
| `/precificar` | Ajuda a definir quanto cobrar por um projeto, com base no escopo real. |
| `/proposta-comercial` | Gera a proposta a partir do que já está no cadastro do cliente. |

---

## Como as pastas se organizam

```
sua-agencia/
├── agencia/          ← quem você é: identidade, stack, preços, nichos
├── clientes/         ← uma pasta por cliente, isolada das outras
│   └── exemplo/      ← um cliente fictício, pra você ver antes do primeiro real
└── .claude/skills/   ← as skills acima
```

`agencia/nichos/` é o seu ponto de partida por tipo de negócio — clínica,
restaurante, advocacia, salão. Em vez de encarar uma tela em branco, você começa
de uma direção que já funciona para aquele ramo e adapta ao cliente.

---

## Antes de sair criando

Duas coisas que economizam retrabalho:

**Cada cliente vive na pasta dele.** O sistema nunca mistura os dados de um com
os de outro. Quando você abrir uma sessão, diga com qual cliente está trabalhando.

**O site é do cliente, não seu.** As cores, a fonte e o tom saem da marca dele.
Sua identidade em `agencia/` serve para as suas peças — propostas, apresentações —
nunca é empurrada para dentro da entrega.

---

## Quando travar

Refaça o passo com o Claude aberto e descreva o que você esperava e o que
aconteceu. A maioria das travadas cai em duas ou três rodadas quando você dá o
contexto certo em vez de repetir o mesmo pedido.
