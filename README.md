# 🧑‍🎓 Aluno Curioso

Um bot que faz o papel do **aluno curioso** para você estudar para concurso usando a
**técnica de Feynman**: você só aprende de verdade quando consegue ensinar. Em vez de
você fazer perguntas, é o bot que te enche de perguntas — pedindo definições, exemplos,
"por quê?", comparações e "como isso cai na prova?" — te obrigando a explicar melhor.

## Como usar

Não precisa instalar nada, nem ter conta, nem internet.

1. Abra o arquivo **`index.html`** no seu navegador (dois cliques nele já resolve).
2. Escolha um assunto da sua matéria e comece a **explicar** com suas palavras.
3. O aluno vai te interromper com perguntas. Responda explicando — e perceba onde você
   trava: **é exatamente o que você ainda não domina.**

> A conversa fica salva só na sua máquina (no `localStorage` do navegador). Nada é
> enviado para a internet.

## Recursos

- **Níveis de curiosidade** (canto superior direito):
  - **Tranquilo** — aceita mais, confirma o que entendeu.
  - **Curioso** — equilíbrio (padrão).
  - **Implacável** — cava fundo, procura exceções e pegadinhas.
- **Perguntas variadas e contextuais:** o bot lê o que você escreve, identifica os
  termos-chave e escolhe a melhor pergunta (definição, exemplo, causa, consequência,
  comparação, resumo de confirmação, foco em prova...).
- **Pede para você resumir** de tempos em tempos ("deixa eu ver se entendi: ...") para
  forçar a consolidação.
- **⬇ Resumo:** baixa a conversa inteira como um arquivo `.md` para você revisar depois.
  Os pontos em que o aluno mais insistiu são bons candidatos a revisão.
- **↻ Nova sessão:** zera para começar outro assunto.

## Dicas para aproveitar (técnica de Feynman)

1. **Explique como se fosse para uma criança** — sem jargão escondendo a dúvida.
2. Quando travar numa pergunta do bot, **volte ao material**, entenda, e explique de novo.
3. Use o nível **Implacável** quando achar que já domina o tema — ele vai testar isso.
4. Ao final, baixe o **Resumo** e releia: o que ficou confuso na sua explicação é o que
   precisa de mais estudo.

## Como funciona por dentro

É um único arquivo HTML com um motor de perguntas em JavaScript puro. Ele faz uma
análise leve do texto em português (extrai termos-chave por capitalização e por palavras
técnicas mais longas, ignora palavras comuns) e sorteia, de forma ponderada, a estratégia
de pergunta mais adequada ao que você acabou de dizer — evitando repetir a mesma
abordagem ou perguntar duas vezes sobre o mesmo termo.

Por rodar 100% offline, o bot é "curioso por heurística", não por um modelo de linguagem.
Isso o torna gratuito e instantâneo. Se um dia você quiser deixá-lo ainda mais esperto
com IA de verdade (a API da Claude/Anthropic, por exemplo), dá para evoluir o motor de
perguntas para chamar um modelo — mas para a prática diária de explicar a matéria, a
versão atual já cumpre muito bem o papel.
