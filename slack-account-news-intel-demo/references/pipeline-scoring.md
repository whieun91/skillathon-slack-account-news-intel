# Pipeline Scoring

Use this reference to rank accounts for weekly pipeline generation while preserving the broader intelligence report.

## Goal

Help the user identify about 10 qualified pipeline candidates per week. Prioritize accounts with a credible reason to contact now, not merely interesting news.

## Score Dimensions

Score each dimension from 0 to 5, then assign a grade.

| Dimension | What to look for |
| --- | --- |
| News timing | Recent, relevant news within the last 7-30 days |
| Business change | Funding, IPO, growth, hiring, global expansion, new products, DX/AX, M&A |
| Usage signal | active > licensed, high utilization, low utilization risk, active teams likely expanding |
| Plan motion fit | Clear upgrade, Enterprise+, seat expansion, Slack Connect, governance, AI/Salesforce, or renewal-defense motion |
| Hook clarity | The AE can write a specific, natural first message from the signal |
| Confidence | Source quality, account-name match, and data reliability |

## Grades

- A: Contact this week. Strong news or usage signal, clear hook, specific commercial motion.
- B: Nurture or validate within 2 weeks. Good signal but missing stakeholder, usage clarity, or stronger source.
- C: Monitor. Interesting but not enough reason to contact now.
- Exclude: weak source, irrelevant news, no usage context, too small or inactive, or only speculative connection.

## Recommended Top 10 Columns

```markdown
| 순위 | 고객사 | 플랜 | 점수/등급 | 근거 | 후킹 포인트 | 추천 모션 | 컨택 타이밍 | 첫 액션 |
| ---: | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Demo Travel Platform | Business+ | A | 성장 뉴스 + active > licensed | 글로벌 확장과 파트너 협업 증가 | Enterprise+ 검토 | 이번 주 | 기사 기반 메시지 발송 |
```

## Guardrails

- Do not force exactly 10 if fewer than 10 accounts have credible signals. Say "이번 주 강한 후보는 N개" and list B-grade nurtures separately.
- Do not count risk-only accounts as pipeline unless there is a renewal, expansion, or recovery motion.
- For Enterprise accounts, avoid "plan upsell"; score seat, workspace, workflow, AI/Salesforce, Slack Connect, governance, or renewal motions.
- For Free and Pro accounts, score paid conversion and Business+/Enterprise+ potential.
- If usage data conflicts with common sense, mark "사용량 정의 확인 필요" before treating it as pipeline.
