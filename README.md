🧠 Prompts de Agentes de IA

Coleção de system prompts prontos para uso, criados para transformar um LLM (ChatGPT, Claude, Copilot Chat, etc.) em um copiloto técnico de desenvolvimento com comportamento, personalidade e regras bem definidas — cada um especializado em uma etapa diferente do fluxo de trabalho de programação.

A stack de referência dos prompts é Node.js + TypeScript, mas todos os arquivos têm seções marcadas como (EDITÁVEL), então é fácil adaptar para outra stack, linguagem ou domínio.

📂 Estrutura do repositório
prompts-de-agentes-de-IA/
└── prompts/
    ├── promptAgent.md   # Modo AGENT CODE — implementa mudanças reais
    ├── promptAsk.md     # Modo ASK — responde dúvidas, só leitura
    ├── promptPlan.md    # Modo PLAN — planeja antes de codar
    └── promptStudy.md   # Modo STUDY — ensina e explica conceitos
🎭 Os 4 modos

Cada prompt define uma identidade, uma personalidade própria e regras específicas de comportamento — pensados para funcionar como "personas" separadas de um mesmo copiloto, cada uma adequada a um momento diferente do trabalho.

Arquivo	Modo	Persona	Foco
promptAgent.md	AGENT CODE	Luna — calorosa, confiante, levemente sarcástica	Gera código pronto para colar, segue o ciclo Descobrir → Planejar → Implementar → Verificar → Finalizar
promptAsk.md	ASK (somente leitura)	Atenas — paciente, ponderada, mentora sábia	Explica código, diagnostica erros e sugere abordagens sem aplicar mudanças
promptPlan.md	PLAN	Jarvis — polido, pragmático, humor seco	Produz um plano de implementação estruturado e revisável, sem escrever código completo
promptStudy.md	STUDY	Bianca — animada, didática, "parceira de crime"	Ensina conceitos com analogias, progressão de dificuldade e checkpoints de compreensão
Estrutura comum a todos os prompts

Cada arquivo segue o mesmo esqueleto:

IDENTIDADE — papel do assistente naquele modo.
STACK (EDITÁVEL) — tecnologias assumidas (Node.js, TypeScript, framework, testes, lint, banco, infra), com regra de assumir a opção mais provável quando faltar informação.
PERSONALIDADE (EDITÁVEL) — tom de voz, nome do assistente e exemplos de fala.
Regras do modo — o que o assistente pode e não pode fazer (ex.: ASK nunca edita arquivos; PLAN nunca entrega código pronto; AGENT sempre entrega diffs).
Formato de resposta — estrutura que a resposta deve seguir (quando aplicável).
Perguntas/checkpoints — limite de perguntas de esclarecimento antes de assumir e seguir em frente.
🚀 Como usar
Escolha o modo de acordo com o momento do trabalho:
Quer entender algo → promptStudy.md
Quer planejar antes de codar → promptPlan.md
Quer tirar dúvida ou diagnosticar um erro sem alterar nada → promptAsk.md
Quer que o assistente implemente de fato → promptAgent.md
Copie o conteúdo do arquivo escolhido e cole como system prompt (instruções) da sua ferramenta de IA.
Edite as seções STACK e PERSONALIDADE conforme seu projeto e preferência de tom.
Converse normalmente — o assistente já vai seguir as regras e o formato definidos no prompt.

💡 Dica: você pode manter os quatro prompts salvos como presets/personas diferentes na sua ferramenta de IA e alternar entre eles conforme a etapa do trabalho.

🛠️ Personalizando para sua stack

Todos os prompts assumem Node.js/TypeScript por padrão, com placeholders como {FRAMEWORK}, {TEST_FRAMEWORK}, {DB} e {DEPLOY} (mais evidentes em promptAgent.md). Para adaptar:

Substitua os placeholders pelas tecnologias reais do seu projeto (ex.: Python/Django, Go, PHP/Laravel).
Ajuste a seção de PERSONALIDADE para o tom que fizer sentido para você — ou remova essa seção se preferir um assistente neutro.
Mantenha as regras do modo, que são a parte que garante o comportamento consistente (ex.: ASK não aplica mudanças, PLAN não escreve código completo).
📄 Licença

Nenhuma licença foi definida neste repositório até o momento.

Feito para quem quer um copiloto de IA mais previsível e com papéis bem definidos — em vez de um único assistente genérico tentando fazer tudo ao mesmo tempo.
