# 🧭 Assistente de Planejamento com IA — Método CPER

> Projeto Final da Trilha · Assistente que transforma qualquer objetivo (estudo, carreira ou negócio) em um plano executável, encaixado na rotina e revisado toda semana, usando o **Notion** como fonte de verdade.

---

## 1. Visão geral

O assistente segue o meu método de planejamento em 4 etapas, cada uma ensinada à IA por uma **habilidade (skill)**:

| Etapa | Habilidade | Pergunta que responde | Banco no Notion |
|---|---|---|---|
| **C**larear | [`esclarecer-objetivo`](skills/01-esclarecer-objetivo.md) | Onde exatamente quero chegar, e até quando? | Objetivos |
| **P**lanejar | [`montar-plano`](skills/02-montar-plano.md) | Quais marcos e tarefas me levam lá? O que pode dar errado? | Plano de Ação · Obstáculos |
| **E**ncaixar | [`encaixar-rotina`](skills/03-encaixar-rotina.md) | Quando, na minha semana real, eu faço isso? | Rotina |
| **R**evisar | [`revisar-progresso`](skills/04-revisar-progresso.md) | Estou no ritmo? O que ajusto? | Acompanhamento |

```
Objetivo vago ──► [C] Clarear ──► [P] Planejar ──► [E] Encaixar ──► execução
                                        ▲                               │
                                        └──────── [R] Revisar ◄─────────┘
                                                   (toda semana)
```

### O que adaptei do Planner da Trilha
- **Critério de sucesso obrigatório** no objetivo: sem ele, a IA não avança para o plano.
- **Regra dos 80%:** o plano nunca ocupa mais que 80% das horas declaradas (folga para imprevistos).
- **Planos se-então** para cada obstáculo, em vez de só listar riscos.
- **Versão mínima** de cada bloco da rotina (ex.: 15 min) para manter a constância em dias ruins.
- **Revisão 3P** (Placar · Porquês · Próximos passos) com regras de decisão objetivas.

---

## 2. Estrutura do Planner no Notion

Página-mãe **🧭 Planner** com 5 bancos de dados relacionados:

### 2.1 Objetivos
| Propriedade | Tipo |
|---|---|
| Objetivo | Título |
| Tipo | Seleção: Estudo · Carreira · Negócio |
| Critério de sucesso | Texto |
| Prazo | Data |
| Porquê | Texto |
| Ponto de partida | Texto |
| Horas/semana | Número |
| Status | Status: Planejando · Em andamento · Pausado · Concluído |
| Progresso | Rollup (% de tarefas concluídas no Plano de Ação) |

### 2.2 Plano de Ação
| Propriedade | Tipo |
|---|---|
| Tarefa | Título (começa com verbo) |
| Objetivo | Relação → Objetivos |
| Marco | Seleção |
| Duração (h) | Número |
| Prioridade | Seleção: Essencial · Importante · Se der |
| Prazo | Data |
| Bloco | Relação → Rotina |
| Status | Status: A fazer · Fazendo · Feito |

**Visões:** Quadro por status · Linha do tempo por marco · "Esta semana" (filtro por prazo).

### 2.3 Rotina
| Propriedade | Tipo |
|---|---|
| Bloco | Título |
| Dias | Multisseleção |
| Horário | Texto |
| Energia | Seleção: 🟢 Alta · 🟡 Média · 🔵 Baixa |
| Versão mínima | Texto |
| Tarefas | Relação → Plano de Ação |

### 2.4 Obstáculos
| Propriedade | Tipo |
|---|---|
| Obstáculo | Título |
| Gatilho | Texto |
| Resposta se-então | Texto |
| Ocorrências | Número |
| Objetivo | Relação → Objetivos |

### 2.5 Acompanhamento
| Propriedade | Tipo |
|---|---|
| Semana | Título (ex.: "2026-S49") |
| % execução | Número (%) |
| Horas realizadas | Número |
| Energia (1–5) | Número |
| O que funcionou | Texto |
| O que travou | Texto |
| Ajuste | Texto |
| Próximas 3 prioridades | Texto |

---

## 3. Como a IA usa as habilidades

**Instrução de sistema do assistente** (cole no projeto/agente da sua IA):

```text
Você é um assistente de planejamento que segue o Método CPER.
Fonte de verdade: o Planner no Notion (bancos Objetivos, Plano de Ação,
Rotina, Obstáculos, Acompanhamento).

Siga as etapas na ordem e não pule nenhuma:
1. esclarecer-objetivo  — se o objetivo não tem critério de sucesso, prazo e horas/semana.
2. montar-plano         — se o objetivo está claro mas não há tarefas.
3. encaixar-rotina      — se há tarefas sem bloco na rotina.
4. revisar-progresso    — na revisão semanal ou quando o usuário perguntar "como estou?".

Regras gerais:
- Leia o Notion antes de responder; grave no Notion só após o usuário aprovar.
- No máximo 5 perguntas por vez.
- Nunca ocupe mais de 80% das horas declaradas.
- Seja direto e honesto sobre atrasos. Nunca altere prazos sem confirmação.
```

**Gatilhos de conversa**

| O usuário diz… | Habilidade acionada |
|---|---|
| "Quero aprender…", "Meu objetivo é…" | esclarecer-objetivo |
| "Monta o plano", "Por onde começo?" | montar-plano |
| "Não acho tempo", "Organiza minha semana" | encaixar-rotina |
| "Revisão da semana", "Como estou indo?" | revisar-progresso |

---

## 4. Demonstração (dados fictícios)

> **Persona fictícia:** Carla Mendes, 34 anos, assistente administrativa em uma distribuidora. Trabalha das 8h às 17h, tem 1h de deslocamento por trecho e um filho de 6 anos. Excel intermediário, nunca usou SQL nem Python.

### 4.1 Clarear

> **Carla:** Quero mudar pra área de dados.
>
> **Assistente:** Entendi: você quer migrar para uma função de dados. Para transformar isso em um objetivo claro, 5 perguntas:
> 1. Que cargo seria "chegar lá"? 2. Até quando? 3. Por que agora? 4. O que já sabe? 5. Quantas horas por semana consegue dedicar?
>
> **Carla:** Analista de dados júnior. Até o meio de 2027. Quero sair do operacional e ganhar mais. Sei Excel, PROCV e tabela dinâmica. Umas 8 horas por semana.
>
> **Assistente:** Proposta de objetivo:
> **"Ser contratada como analista de dados júnior até 30/06/2027."**
> Critério de sucesso: proposta aceita. Teste de realismo: 30 semanas × 8 h = 240 h; usando 80%, ficamos com ~190 h. Para júnior partindo de Excel, é apertado mas viável se o plano for enxuto. Confirma?
>
> **Carla:** Confirmo.

**Registro em Objetivos**

| Objetivo | Tipo | Critério | Prazo | Horas/sem | Status |
|---|---|---|---|---|---|
| Ser contratada como analista de dados júnior | Carreira | Proposta aceita | 30/06/2027 | 8 | Em andamento |

### 4.2 Planejar

**Marcos (de trás para frente)**

| # | Marco | Período | Entrega verificável | Horas |
|---|---|---|---|---|
| M1 | Fundamentos de SQL | 01/12 – 04/01 | 50 exercícios resolvidos + certificado | 30 |
| M2 | Python e pandas | 05/01 – 15/02 | Notebook de análise de vendas no GitHub | 40 |
| M3 | Power BI | 16/02 – 22/03 | Dashboard publicado | 32 |
| M4 | Portfólio | 23/03 – 03/05 | 2 projetos completos + LinkedIn atualizado | 40 |
| M5 | Candidaturas e entrevistas | 04/05 – 30/06 | 40 candidaturas, 5 entrevistas | 36 |
| | **Total** | 30 semanas | | **178 h** (74% da capacidade ✅) |

**Primeiras tarefas (M1)**

| Tarefa | Duração | Prioridade | Prazo | Status |
|---|---|---|---|---|
| Criar conta no curso e instalar o SQLite/DBeaver | 0,5 h | Essencial | 01/12 | Feito |
| Assistir módulo 1 — SELECT e WHERE | 2 h | Essencial | 04/12 | Feito |
| Resolver 10 exercícios de filtros | 1,5 h | Essencial | 06/12 | Feito |
| Assistir módulo 2 — GROUP BY | 2 h | Importante | 06/12 | A fazer |

**Obstáculos mapeados**

| Obstáculo | Gatilho | Resposta se-então |
|---|---|---|
| Cansaço depois do trabalho | Chegar em casa após 19h | Se chegar depois das 19h, então faço só a versão mínima (15 min de exercícios). |
| Filho doente / imprevisto familiar | Dia sem bloco cumprido | Se perder um bloco, então uso o bloco-coringa de domingo. |
| Travar em um exercício | Mais de 20 min no mesmo problema | Se travar 20 min, então anoto a dúvida, pulo e pergunto no fórum/IA. |

### 4.3 Encaixar

| Bloco | Dias | Horário | Energia | Versão mínima |
|---|---|---|---|---|
| Foco cedo | Ter, Qui | 6h30 – 7h30 | 🟢 | 20 min de exercício |
| Bloco longo | Sáb | 9h – 12h | 🟢 | 1 h |
| Revisão leve | Seg, Qua | 21h – 21h30 | 🔵 | 10 min de leitura |
| Coringa | Dom | 16h – 17h | — | Livre (só para atrasos) |

Total planejado: **6 h/semana** (+1 h coringa) de 8 h declaradas → dentro da regra dos 80%.

### 4.4 Revisar (semana 1)

> **Carla:** Revisão da semana.
>
> **Assistente — Placar:** 3 de 4 tarefas feitas (**75%**), 4 h de 6 h planejadas. M1 em 13%, faltam 4 semanas.
> **Porquês:** o que funcionou? o que travou? energia de 1 a 5?
>
> **Carla:** Os blocos de manhã funcionaram. Perdi o sábado por aniversário de família. Energia 4.
>
> **Assistente — Próximos passos:** Execução entre 50% e 79% → ajuste de rotina, sem replanejar.
> - Ajuste: quando houver evento no sábado, o bloco longo passa para domingo 9h–12h.
> - Prioridades: (1) Módulo 2 — GROUP BY; (2) 10 exercícios de agregação; (3) Módulo 3 — JOIN.
> - Registrei "Evento familiar no sábado" como obstáculo novo. Posso gravar?

**Registro em Acompanhamento**

| Semana | % execução | Horas | Energia | Funcionou | Travou | Ajuste |
|---|---|---|---|---|---|---|
| 2026-S49 | 75% | 4 | 4 | Blocos das 6h30 | Sábado ocupado | Sábado → domingo quando houver evento |

---

## 5. Como replicar

1. Duplique o Planner da Trilha no Notion e adicione as propriedades da seção 2.
2. Crie as 4 habilidades a partir dos arquivos em [`skills/`](skills/).
3. Cole a instrução de sistema da seção 3 no seu assistente e conecte-o ao Notion.
4. Comece com: *"Quero planejar um objetivo novo."*
5. Agende a revisão semanal (sugestão: domingo à noite, 15 min).

## 6. Limitações
- A IA depende da honestidade dos registros: se a tarefa não for marcada no Notion, o placar fica errado.
- Estimativas de duração são palpites iniciais; a precisão melhora após 2–3 revisões.
- Os dados da demonstração são **fictícios** e servem apenas para ilustrar o método.

---

```
assistente-planner/
├── README.md                         ← esta documentação
└── skills/
    ├── 01-esclarecer-objetivo.md
    ├── 02-montar-plano.md
    ├── 03-encaixar-rotina.md
    └── 04-revisar-progresso.md
```
