---
name: esclarecer-objetivo
description: Use quando o usuário trouxer um objetivo novo (estudo, carreira ou negócio) ou um objetivo vago. Transforma a intenção em um objetivo claro, mensurável e com prazo, e registra no banco "Objetivos" do Planner.
---

# Habilidade 1 — Esclarecer o objetivo

## Propósito
Nenhum plano é melhor que o objetivo que o originou. Esta habilidade impede que a IA monte um plano em cima de uma intenção vaga ("quero aprender dados", "quero crescer meu negócio").

## Quando acionar
- O usuário diz "quero…", "preciso…", "meu objetivo é…".
- Existe um objetivo no Notion com o campo **Critério de sucesso** vazio.

## Passo a passo
1. **Reformule** o que entendeu em uma frase e peça confirmação.
2. **Faça no máximo 5 perguntas**, uma rodada só, escolhendo entre:
   - **Resultado:** como você saberá que chegou lá? (número, entrega, evento)
   - **Prazo:** até quando? Existe uma data externa (prova, vaga, lançamento)?
   - **Porquê:** por que isso importa agora? (vira a frase de motivação do objetivo)
   - **Ponto de partida:** o que você já sabe/tem hoje?
   - **Restrições:** horas por semana, orçamento, ferramentas, compromissos fixos.
3. **Classifique** o tipo: `Estudo`, `Carreira` ou `Negócio`.
4. **Escreva o objetivo** no formato:
   > **Verbo + resultado mensurável + prazo**
   > Ex.: "Ser contratada como analista de dados júnior até 30/06/2027."
5. **Teste de realismo:** compare horas disponíveis × tamanho do objetivo. Se não fecha, proponha *duas* alternativas (estender prazo ou reduzir escopo) e deixe o usuário escolher.
6. **Registre** no banco `Objetivos` e só então passe para a Habilidade 2.

## Regras
- Não monte o plano nesta etapa.
- Não invente prazo nem número: se o usuário não souber, ofereça uma sugestão marcada como *sugestão*.
- Um objetivo por vez. Se vierem três, peça para priorizar.

## Saída esperada (Notion → Objetivos)
| Campo | Exemplo |
|---|---|
| Objetivo | Ser contratada como analista de dados júnior |
| Tipo | Carreira |
| Critério de sucesso | Proposta de emprego aceita |
| Prazo | 30/06/2027 |
| Porquê | Sair da rotina administrativa e ganhar 30% a mais |
| Ponto de partida | Excel intermediário, zero SQL/Python |
| Horas/semana | 8 h |
| Status | Planejando |
