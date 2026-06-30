# 🧑‍🎓 Aluno Curioso — PPRS 2026

Um bot que faz o papel do **aluno curioso** para você estudar para o concurso da
**Polícia Penal do Rio Grande do Sul (PPRS 2026)** usando a **técnica de Feynman**:
você só aprende de verdade quando consegue ensinar. Em vez de você fazer perguntas,
é o bot que te enche de perguntas — pedindo definições, exemplos, "por quê?",
comparações e "como isso cai na prova?" — te obrigando a explicar melhor.

## Como usar

Não precisa instalar nada, nem ter conta, nem internet.

1. Abra o arquivo **`index.html`** no seu navegador (dois cliques nele já resolve).
2. Clique em uma **matéria do edital** (chips embaixo) ou comece a explicar o que quiser.
3. O aluno vai te interromper com perguntas. Responda explicando — e perceba onde você
   trava: **é exatamente o que você ainda não domina.**

> A conversa fica salva só na sua máquina (no `localStorage` do navegador).

## Matérias (edital PPRS 2026)

A prova objetiva tem 80 questões. Os chips do bot seguem as disciplinas do edital:

- **Língua Portuguesa**
- **Informática**
- **Raciocínio Lógico**
- **Legislação Aplicada / Direito**
- **Lei de Execução Penal (LEP)**
- **Sistema Prisional** (SUSEPE, Polícia Penal, Regras de Mandela, etc.)

## Recursos

- **Níveis de curiosidade** (Tranquilo / Curioso / Implacável) — o quanto o aluno te cobra.
- **Perguntas variadas e contextuais:** definição, exemplo, causa, consequência, comparação,
  resumo de confirmação e foco em prova.
- **🔁 Recall (revisão ativa):** depois de algumas rodadas, o aluno volta e te pede para
  re-explicar um conceito antigo, sem olhar — o jeito mais eficaz de fixar.
- **📝 Quiz:** gera 5 perguntas a partir do que vocês conversaram, para você se autotestar.
- **⬇ Resumo:** baixa a conversa como `.md` para revisar depois.
- **↻ Nova sessão:** zera para começar outra matéria.

## 🤖 Modo IA (opcional)

Por padrão o bot usa um **motor offline** (curioso por heurística): rápido, grátis e sem
internet, mas não entende o conteúdo a fundo. Se quiser um aluno que **realmente entende a
matéria e aponta quando você explica algo errado**, ative o Modo IA (botão 🤖 IA):

- **WebLLM** — um modelo de verdade rodando 100% no seu navegador, **sem chave**. Precisa de
  Chrome/Edge recentes (WebGPU) e baixa o modelo uma vez (~1 GB, fica em cache). Depois roda
  offline.
- **Chave da Claude (Anthropic)** — melhor qualidade e resposta instantânea, se você tiver
  uma `ANTHROPIC_API_KEY`. A chave fica salva só na sua máquina.

Se a IA falhar (sem WebGPU, sem rede, chave inválida), o app volta sozinho para o motor
offline — nada quebra.

> ⚠️ O Modo IA foi escrito de forma defensiva mas **não pôde ser testado no ambiente onde o
> app foi gerado** — vale conferir no seu navegador.

## Dica de uso (técnica de Feynman)

1. Explique como se fosse para alguém que nunca estudou o assunto — sem jargão escondendo a dúvida.
2. Quando travar numa pergunta do bot, volte ao material, entenda, e explique de novo.
3. Use o nível **Implacável** quando achar que já domina o tema.
4. No fim, gere o **Quiz** e baixe o **Resumo** para revisar o que ficou frágil.

## Como funciona por dentro

Um único arquivo HTML com um motor de perguntas em JavaScript puro. Ele faz uma análise leve
do texto em português (extrai termos-chave, ignora palavras comuns) e sorteia, de forma
ponderada, a melhor estratégia de pergunta para o que você acabou de dizer — evitando repetir
a mesma abordagem e cobrando conceitos antigos de volta (recall). O Modo IA é uma camada
opcional por cima, que delega a geração das perguntas a um modelo (WebLLM local ou Claude).
