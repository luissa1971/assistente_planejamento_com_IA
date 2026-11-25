---
name: encaixar-rotina
description: Use depois que o plano for aprovado, ou quando o usuário disser que não está achando tempo. Distribui as tarefas em blocos fixos da semana real do usuário e grava no banco "Rotina" do Planner.
---

# Habilidade 3 — Encaixar o plano na rotina

## Propósito
Plano que não tem hora marcada vira lista de desejos. Esta habilidade converte tarefas em **blocos de agenda** respeitando a vida real do usuário.

## Passo a passo
1. **Levante a semana-tipo** (se ainda não existir no Notion): horários de trabalho, deslocamento, família, sono, compromissos fixos.
2. **Identifique janelas** livres de 30 min ou mais e classifique a energia:
   - 🟢 Alta (foco profundo) · 🟡 Média · 🔵 Baixa (tarefas leves, revisão)
3. **Crie blocos recorrentes** com nome e duração fixos (ex.: "Bloco SQL — ter/qui 6h30–7h30").
4. **Encaixe as tarefas:**
   - Essenciais e difíceis → janelas 🟢.
   - Leitura, vídeo, organização → 🟡/🔵.
   - Mantenha **1 bloco-coringa por semana** vazio para atrasos.
5. **Defina a versão mínima** de cada bloco (ex.: "se o dia estiver ruim, faça 15 min"). Isso protege a constância.
6. **Confirme** com o usuário e grave no banco `Rotina` (e, se ele quiser, no calendário).

## Regras
- Nunca ocupe mais de 80% das horas que o usuário declarou.
- Não marque blocos em horário de sono ou de compromisso fixo.
- No máximo 2 blocos de foco profundo por dia.

## Saída esperada (Notion → Rotina)
Bloco · Dia(s) · Horário · Energia · Tarefas vinculadas · Versão mínima
