# Fase 1 — Playbook de coleta (só quando há site atual)

Objetivo: se o cliente já tem um site, garantir que nenhum dado nem imagem boa fica pra
trás antes de reescrever tudo do zero. Regra de ouro: **se o dado está no site do cliente,
é obrigação achar** — não se contentar com "abri a home e não vi".

Se o cliente **não tem site atual**, pule esta fase: o que existe já está no `CLIENTE.md`
(preenchido pelo `/novo-cliente`) e nas fotos de `assets/`. Vá direto pra Fase 2.

## 1. Vasculhar o site atual, página por página

Abrir só a home e puxar o texto renderizado costuma perder dado — menu, rodapé e páginas
internas (contato, serviços, convênios, equipe) escondem informação que não está na
primeira tela. Navegue pelo site de verdade:

- Abra cada link do menu principal e do rodapé (Contato, Sobre, Serviços, Convênios,
  Equipe, Horário) e leia o texto de cada página.
- Confira `sitemap.xml` e `robots.txt` do domínio — às vezes revelam página que não está
  no menu.
- Se o site for lento, com SSL vencido, ou carregar conteúdo via JavaScript, use o
  navegador (Playwright/`claude-in-chrome`) pra abrir e ler o texto já renderizado, em vez
  de tentar puxar o HTML cru.

Procure especificamente: telefone e WhatsApp (`wa.me/`, `api.whatsapp.com`), e-mail,
endereço, horário de funcionamento, convênios/formas de pagamento, redes sociais, link de
portal/login/agendamento se existir, diferenciais que o próprio cliente já escolheu
destacar.

## 2. Baixar as imagens reais

As fotos que já existem no site do cliente valem ouro (ambiente real, equipe, produtos,
logo em boa resolução). Baixe as boas — descarte ícone, sprite e logo de terceiro — e
salve em `clientes/[nome-cliente]/assets/`. Anote no `CLIENTE.md` quais existem e onde
ainda falta imagem (aí a Fase 2 decide: banco de imagens coerente ou gerada por IA).

## 3. Pesquisar fora do site

- **Busca do nome + cidade:** Google Business (nota, avaliações, horário oficial — às
  vezes diverge do site), notícias, tempo de mercado.
- **Instagram/Facebook:** tom da marca, fotos reais, provas sociais, posts que mostram o
  serviço na prática.
- **1-2 concorrentes diretos:** só como referência de linguagem do segmento, nunca pra
  copiar.

## 4. Atualizar o `CLIENTE.md`

Não crie um arquivo novo — complete o `CLIENTE.md` do cliente com o que foi achado.
Preste atenção especial a:

- **O que diferencia:** se o `/novo-cliente` deixou vago ("qualidade", "atendimento"),
  veja se o site atual ou as redes têm algo mais concreto.
- **O que evitar:** anote em uma linha o que está ruim no site atual (visual datado, texto
  confuso, sem WhatsApp visível) — o novo site não pode repetir.
- **Pendente com o cliente:** só o que faltou de verdade e é essencial pra seguir.

## ⛔ Checkpoint 1 (obrigatório)

Mostre um resumo organizado: contatos confirmados, imagens baixadas, o que mudou/foi
achado, e as lacunas que sobraram. Pergunte de forma direta:

> "É isso? Confere? Falta algum dado ou alguma imagem antes de eu desenhar o site?"

Só avance pra Fase 2 depois do "sim" ou do "pode seguir".
