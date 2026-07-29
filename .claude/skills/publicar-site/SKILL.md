---
name: publicar-site
description: >
  Coloca o site do cliente no ar e devolve o link público. Use quando o operador
  disser "publicar", "colocar no ar", "subir o site", "gerar o link", "mandar
  pro cliente ver". Para antes de qualquer coisa que envolva domínio pago ou
  dado de cartão — essa etapa é sempre do operador.
---

# Skill: Publicar Site

É o momento em que o trabalho vira algo que existe no mundo. Também é onde mais
gente trava — porque envolve criar contas e ver telas que nunca viu.

Conduza com calma. Um passo por vez, confirmando antes de seguir.

## Antes de publicar

1. Confirme qual cliente e que o site em `clientes/<cliente>/site/` está pronto.
2. **Peça autorização explícita.** Publicar é um ato público. Mostre o que vai
   ao ar e espere o "pode subir".
3. Rode uma última conferência: links funcionando, botão de WhatsApp com o
   número certo, nenhum texto de preenchimento sobrando, nada inventado.

## O caminho padrão: GitHub → Vercel

Duas contas gratuitas, criadas uma vez e reaproveitadas em todos os clientes:

- **GitHub** — guarda os arquivos e o histórico
- **Vercel** — hospeda e publica, de graça, com link próprio

O motivo de usar os dois juntos: a partir daí, **toda alteração que você fizer no
site vai ao ar sozinha**. Você corrige um texto, salva, e em segundos está no ar.
Sem esse caminho, cada ajuste vira um reenvio manual de arquivos.

### Passo 1 — Contas

Verifique o que já existe antes de mandar alguém criar conta:

- `git config user.name` e `git config user.email` estão configurados?
- A pessoa já tem conta no GitHub? E na Vercel?

Se faltar alguma, conduza a criação. Ao criar a conta da **Vercel**, oriente a
entrar **com o GitHub** — isso já conecta os dois e evita uma configuração extra
depois.

Deixe claro: **as duas são gratuitas** e o plano grátis atende sites de negócio
local com folga. Ninguém precisa colocar cartão para publicar.

### Passo 2 — Subir para o GitHub

Crie o repositório para o site do cliente e envie os arquivos.

Duas coisas importantes:

- **Um repositório por cliente.** Nunca junte sites de clientes diferentes no
  mesmo lugar (ver Regra Zero no `CLAUDE.md`).
- **Repositório privado**, por padrão. É o site de um cliente pagante, não uma
  peça de portfólio pública — a menos que ele autorize.

Se for a primeira vez da pessoa, explique em uma linha o que está acontecendo:
"estou mandando os arquivos do site para uma pasta na nuvem, que é de onde a
Vercel vai publicar".

### Passo 3 — Publicar na Vercel

Conecte o repositório na Vercel e publique. Para um site em HTML puro não há
configuração de build: é só apontar para a pasta certa e publicar.

Em segundos sai um link parecido com `nome-do-projeto.vercel.app`. **Esse é o
link para mandar ao cliente ver.**

### Passo 4 — Testar de verdade

Antes de mandar para o cliente, abra o link e confira:

- Todas as páginas carregam
- O menu funciona
- Os botões de WhatsApp e telefone abrem certo
- **Abra no celular.** É onde o cliente vai olhar primeiro.
- As imagens aparecem (as que já existem)

Se algo estiver quebrado, conserte e publique de novo antes de mostrar. A
primeira impressão do cliente com o link acontece uma vez só.

### Passo 4b — Medir a velocidade

Com o link no ar, jogue a URL no **`pagespeed.web.dev`** e olhe a **aba Mobile**.

**A meta é 90 ou mais em Performance.** Abaixo disso, o próprio relatório lista o
que corrigir — e quase sempre é imagem grande demais. Corrija, publique de novo,
meça de novo.

Guarde o resultado: **essa captura de tela é material de venda.** Rodar o teste
no site do concorrente do seu cliente e mostrar os dois lado a lado é o argumento
mais fácil de provar que existe nesse serviço. Vale para fechar o próximo
cliente, e vale para justificar o preço deste.

### Passo 5 — Registrar

Anote no `CLIENTE.md`: o link publicado, a data, e o que ficou pendente.

## Domínio próprio

Se o cliente quer `nomedaempresa.com.br` em vez do link da Vercel:

- **Se ele já tem domínio:** é uma configuração de apontamento. Dá para conduzir,
  mas exige acesso ao painel onde o domínio foi registrado — normalmente é o
  próprio cliente ou o contador dele que tem.
- **Se ele não tem:** domínio é **pago** (algo em torno de R$ 40 a R$ 120 por
  ano, no Brasil). **Não compre nada em nome do cliente.** Explique o custo,
  deixe que ele decida e, se possível, que ele registre em nome dele — domínio
  no nome do cliente evita uma dor de cabeça enorme se um dia vocês se
  separarem.

**Pare antes de qualquer tela de pagamento.** Cartão e compra são sempre do
operador ou do cliente, nunca automatizados aqui.

## Quando é só uma demonstração

Se o site é uma **demo descartável** — aquela que você monta para mostrar a um
prospect antes de fechar — não precisa de repositório. Publique direto e trate
como material de venda, sabendo que não vai ser mantido.

Para cliente que pagou, use sempre o caminho completo. Site de cliente evolui, e
sem histórico cada mudança futura é uma reconstrução.

## Se der errado

Erro na publicação quase sempre é uma destas três coisas:

- **Caminho errado da pasta** — a Vercel está olhando para o lugar errado
- **Arquivo principal com nome errado** — a página inicial precisa se chamar
  `index.html`
- **Conta não conectada** — GitHub e Vercel não estão falando

Diga qual é, em português, e resolva. Não mostre a mensagem de erro crua para
alguém que não programa: traduza o que aconteceu e o que vai fazer a respeito.
