# 눈 떠보니 내 고객사가 대박나서 slack 최상위 플랜을 팔게 된 건에 대하여

## 제출 요약

고객사에게 대박 소식이 있는 경우 업셀을 위해 빠르게 컨택하고, 고객사에게 매출 감소 및 사업 축소 등 부정적인 이슈가 발생하는 경우 기존 계약에 대한 계약 해지 리스크를 관리합니다! 

고객사에 대한 공개 된 뉴스와 mock Slack 계정 데이터 정보를 결합해, Slack AE, 인바운드, 아웃바운드 담당자가 이번 주 접근할 계정과 후킹 메시지를 빠르게 정리하도록 돕습니다. 또한 어트리션 가능성이 있는 고객을 사전에 감지하여 리스크를 관리합니다.

제출물은 실제 고객 데이터가 아니라 재현 가능한 mock data를 사용하였습니다. 결과물은 한국어 Markdown 리포트와 Slack에 복사해 붙여넣을 수 있는 요약 메시지를 중심으로 구성했습니다. 다만, 실제로 고객 데이터로 별도 테스트를 했을 때에도 어트리션 이슈 대응 및 업셀 기회 포착에 유의미한 데이터임을 확인하였습니다. 자세한 예시 화면은 제출한 예시 이미지 폴더를 참고해주시기 바랍니다. 

## 해결하려는 문제

AE 및 영업 담당자들은 매번 파이프라인 생성을 위해 고객사의 슬랙 도입 현황, 고객사와의 소통 내역 및 고객 관련 주요 뉴스를 확인합니다. 이와 관련하여 현재는 주요 고객사에 대한 소식을 따로 키워드로 검색해보거나, 고객 문의가 오면 개별적으로 고객에 대한 뉴스를 검색해보고 있습니다. 이 과정은 반복적이고, 일부 주요 고객사를 대상으로만 하기 때문에 전체적인 데이터를 가시적으로 보고 있지는 못합니다. 또한 타이밍을 놓치는 경우도 많습니다. 예를 들어, 수개월 전에 구글 워크스페이스를 도입하면서 협업툴 도입을 검토하고 있다는 뉴스 기사가 나온 고객에게 뒤늦게 전화를 해보면, 이미 다른 툴을 도입한 경우도 있었습니다. 

이 스킬을 통해 정기적으로 고객에 대한 긍정, 부정 뉴스를 확인하고 이를 세일즈로 연결하여 시의 적절한 시기에 업셀 및 리스크 관리를 할 수 있습니다.

이 Skill은 다음 흐름을 재사용 가능한 절차로 정리합니다.

1. 고객사 또는 잠재고객 목록을 정리합니다.
2. 뉴스를 확인하고 신호를 긍정/부정 등으로 분류합니다.
3. mock Slack 플랜/사용량 신호와 결합합니다.
4. 이번 주 컨택 우선순위와 추천 모션을 만듭니다.
5. AE가 바로 사용할 수 있는 리포트와 Slack 요약을 생성합니다.

## 대상 사용자

- Slack AE, CSM, 파트너 세일즈, 세일즈 오퍼레이션 담당자
- Skillathon에서 반복 가능한 업무 절차를 Codex Skill로 정리하려는 참가자
- 실제 고객 데이터 없이 mock data로 세일즈 인텔리전스 workflow를 검증하려는 사용자

## 주요 파일

| 경로 | 역할 |
| --- | --- |
| `slack-account-news-intel-demo/SKILL.md` | Codex가 실제로 따를 Skill 절차, 입력/출력, guardrails |
| `slack-account-news-intel-demo/references/customer-accounts.md` | 제출용 mock 고객/플랜/사용량 데이터 |
| `slack-account-news-intel-demo/references/customer-data-template.md` | 사용자가 실제 입력 형식을 만들 때 참고할 템플릿 |
| `slack-account-news-intel-demo/references/signal-taxonomy.md` | 뉴스 신호 분류 기준 |
| `slack-account-news-intel-demo/references/pipeline-scoring.md` | Pipeline Fit 점수화 기준 |
| `slack-account-news-intel-demo/references/report-template.md` | Markdown 리포트 구조 |
| `slack-account-news-intel-demo/references/slack-summary-template.md` | Slack 복붙용 요약 템플릿 |
| `slack-account-news-intel-demo/reports/demo-run-mock-news-intel-2026-05-16.md` | mock data 기반 데모 실행 결과 |
| `slack-account-news-intel-demo/agents/openai.yaml` | Codex UI 표시용 metadata |

## 입력

이 Skill은 다음 입력을 받을 수 있습니다.

- 고객사 또는 잠재고객 이름과 alias
- 현재 Slack 상태와 플랜: Free, Pro, Business+, Enterprise, Enterprise Grid, Enterprise+
- 계약 인원, 사용 인원, 월간 활성 사용자 등 사용량 신호
- 갱신일, account owner, segment, 전략 메모
- 목표: upsell, Enterprise+ 검토, 신규 도입, 갱신 방어, attrition risk monitoring, weekly pipeline generation

제출 데모에서는 `references/customer-accounts.md`의 fictional mock data만 사용합니다.

## 출력

대표 출력물은 다음과 같습니다.

- 주간 Slack 고객사 뉴스 인텔리전스 Markdown 리포트
- 이번 주 Pipeline 후보 Top N
- 계정별 뉴스 신호, 사용량 신호, 추천 모션, 첫 메시지
- Mermaid 기반 시각 요약
- Slack 채널에 복사해 붙여넣을 수 있는 짧은 요약
- 검증 체크리스트와 한계

## 실행 프롬프트 예시

Codex에서 아래처럼 요청하면 됩니다.

```text
Use $slack-account-news-intel-demo to create a demo-safe Korean Markdown account news report and Slack-ready summary using the mock customer plan and usage data in references/customer-accounts.md. Include this week's pipeline candidates, signal classification, recommended AE actions, first-message hooks, and validation notes. Do not use real customer data, internal usage data, secrets, tokens, or webhook URLs.
```

한국어로는 아래처럼 요청할 수 있습니다.

```text
$slack-account-news-intel-demo를 사용해서 references/customer-accounts.md의 mock 고객 데이터를 기반으로 한국어 계정 뉴스 인텔리전스 리포트와 Slack 복붙용 요약을 만들어줘. 이번 주 Pipeline 후보, 뉴스 신호 분류, 추천 AE 액션, 첫 메시지, 검증 메모를 포함해줘. 실제 고객 데이터, 내부 사용량, API key, token, webhook URL은 사용하지 마.
```

## 검증 체크리스트

- [x] `SKILL.md`에 name, description, workflow, evidence rules, output rules가 있습니다.
- [x] `references/`에 분류 기준, 템플릿, mock data, scoring 기준이 분리되어 있습니다.
- [x] demo report가 mock data로 생성되어 있습니다.
- [x] 실제 고객사명, 실제 Slack 사용량, 내부 계정 메모를 포함하지 않습니다.
- [x] API key, token, webhook URL, password를 포함하지 않습니다.
- [x] `.DS_Store` 같은 로컬 OS 파일은 Git에서 제외합니다.
- [ ] GitHub 제출 후 README, SKILL.md, demo report 링크가 제출 양식에 포함되어야 합니다.

## 민감정보 처리

이 저장소는 Public 제출을 전제로 정리했습니다. 실제 업무 적용 시에도 저장소에는 실제 고객명, 실제 Slack 사용량, 계약 정보, 담당자 정보, 내부 계정 메모, API key, token, webhook URL을 넣지 않아야 합니다.

민감 데이터가 필요한 실제 업무에서는 Codex 세션 안에서만 사용하고, 결과물을 공개 저장소에 올리기 전에 mock data 또는 비식별 샘플로 교체해야 합니다.

## 한계와 다음 확장

- 현재 데모는 mock data 기반이라 실제 고객 관계나 실제 Slack 사용 현황을 의미하지 않습니다.
- 공개 뉴스 URL은 데모 시나리오 설명을 위한 예시입니다.
- 웹 검색, Notion 저장, Slack 전송은 제출 필수 범위가 아니라 선택 확장 항목입니다.
- 다음 확장으로는 CSV 입력 지원, 자동 scoring script, GitHub Actions 기반 lint/check, Notion/Slack connector 기반 저장 또는 공유 workflow를 추가할 수 있습니다.

## 제출 링크에 적을 위치

- GitHub 저장소: `https://github.com/whieun91/skillathon-slack-account-news-intel`
- Skill: `slack-account-news-intel-demo/SKILL.md`
- References: `slack-account-news-intel-demo/references/`
- Demo report: `slack-account-news-intel-demo/reports/demo-run-mock-news-intel-2026-05-16.md`
