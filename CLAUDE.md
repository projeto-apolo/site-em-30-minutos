# Sua agência de sites

Este é o espaço de trabalho de uma agência de criação de sites. Aqui vivem os
clientes, os padrões da agência e as skills que produzem cada entrega.

Não é um projeto de software: não há build, testes ou lint. O trabalho é
orientado por **skills** e por arquivos Markdown. Código de entrega vive dentro
da pasta do cliente.

Quem opera aqui provavelmente **não é programador**. Explique o que está fazendo
em português claro, sem jargão. Quando algo der errado, diga o que aconteceu e
qual é o próximo passo — nunca despeje um erro técnico sem tradução.

---

## ⚠️ Regra Zero — cada cliente é um mundo

**Antes de qualquer ação que envolva um cliente, confirme qual cliente está ativo
e trabalhe somente dentro de `clientes/<nome-do-cliente>/`.**

- Nunca misture arquivos, dados ou contexto de clientes diferentes.
- Se a tarefa não deixa claro de quem se trata, **pergunte antes de agir**.
- Nunca leia a pasta de um cliente para informar a entrega de outro.
- Dados de cliente (contatos, contratos, acessos) nunca saem da pasta dele.

Um vazamento de contexto entre clientes é o erro mais caro que pode acontecer
aqui: gera uma entrega errada e queima a confiança de quem pagou.

---

## O que ler antes de trabalhar

No começo de qualquer tarefa, leia (quando existirem):

1. `agencia/identidade.md` — quem opera a agência, tom de voz, como se apresenta
2. `agencia/stack.md` — tecnologias padrão das entregas
3. `clientes/<cliente>/CLIENTE.md` — o briefing do cliente ativo

Para uma entrega visual, leia também o arquivo do nicho correspondente em
`agencia/nichos/`, se houver um que sirva.

Não anuncie que leu. Apenas use o contexto naturalmente.

---

## Estrutura

```
├── CLAUDE.md                 ← este arquivo
├── .claude/skills/           ← as skills da agência
├── agencia/
│   ├── identidade.md         ← preenchido pelo /instalar
│   ├── stack.md              ← tecnologias padrão
│   ├── precos-referencia.md  ← faixas de preço de mercado
│   └── nichos/               ← direção visual de partida por tipo de negócio
└── clientes/
    ├── _template-cliente/    ← esqueleto copiado a cada cliente novo
    └── <cliente>/
        ├── CLIENTE.md        ← briefing, contato, status
        ├── site/             ← os arquivos do site
        └── assets/           ← logo, fotos, textos que o cliente mandou
```

---

## Skills — qual usar em cada momento

| Skill | Gatilho típico | Saída |
|---|---|---|
| `/instalar` | "configurar", "começar", primeira vez | `agencia/identidade.md` preenchido |
| `/novo-cliente` | "cliente novo", "cadastrar cliente", "fechei um projeto" | `clientes/<nome>/` completo |
| `/criar-site` | "criar site", "fazer landing page", "montar a página" | `clientes/<nome>/site/` |
| `/publicar-site` | "publicar", "colocar no ar", "subir o site" | link público + registro no `CLIENTE.md` |
| `/precificar` | "quanto cobrar", "orçar", "fazer o preço" | faixa recomendada + justificativa |
| `/proposta-comercial` | "fazer proposta", "mandar orçamento" | documento de proposta na pasta do cliente |

Antes de executar qualquer tarefa, verifique se existe skill que a cubra. Se
existir, siga a skill. Se não existir, execute normalmente.

---

## Planeje antes de construir

Para qualquer implementação relevante — um site, uma página, uma reestruturação —
**apresente o plano e valide antes de executar**. Estrutura de seções, direção
visual e conteúdo se acertam conversando, em segundos. Depois de construído, cada
correção custa muito mais.

Isso não vale para tarefas pequenas e óbvias. Vale para tudo que vira entrega.

---

## Aprenda com as correções

Quando o operador corrigir algo ou der uma instrução que soa permanente ("na
verdade é assim", "não faça mais isso", "prefiro assim", "sempre que...",
"evita..."), pergunte:

> "Quer que eu salve isso pra não precisar repetir?"

Se sim, grave onde fizer sentido:

- **Sobre a agência** (como se apresenta, tom, o que evita) → `agencia/identidade.md`
- **Sobre tecnologia** (ferramenta padrão, forma de publicar) → `agencia/stack.md`
- **Sobre preço** → `agencia/precos-referencia.md`
- **Sobre um cliente específico** → o `CLIENTE.md` dele
- **Regra de comportamento geral** → este `CLAUDE.md`

Acrescente uma linha clara, sem reformatar o arquivo inteiro. Mostre a linha que
adicionou.

Não pergunte quando a correção for pontual ("na verdade o arquivo é o outro").
Só quando a informação tiver valor duradouro.

**Se a mesma tarefa manual aparecer três vezes**, sugira transformá-la em skill.
É assim que a agência fica mais rápida com o tempo.

---

## Segurança e limites

- **Nada é publicado sem confirmação.** Site no ar, proposta enviada, conteúdo
  postado — sempre mostre antes e espere o "pode ir".
- **Senhas e tokens de cliente nunca são digitados aqui.** Se uma etapa exigir
  login sensível, peça que o operador faça manualmente.
- **Não invente dados de cliente.** Nome, telefone, endereço, horário, preço:
  se não está no `CLIENTE.md`, pergunte. Um site com informação inventada é pior
  que um site incompleto — o cliente perde credibilidade com quem confia nele.
