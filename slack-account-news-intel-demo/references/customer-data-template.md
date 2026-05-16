# Customer Data Template

Ask the user for data in this shape when account context is needed. Markdown tables are preferred for readability.

```markdown
| account | aliases | current_slack_status | plan | licensed_users | active_users | renewal_date | owner | notes |
| --- | --- | --- | --- | ---: | ---: | --- | --- | --- |
| Demo Travel Platform | DemoTravel, 여행 플랫폼 A | using | Business+ | 250 | 210 | 2026-09-30 | AE name | 여행/레저, 확장 관심 |
| Demo Petcare | DemoPet, 펫케어 스타트업 B | unknown | unknown |  |  | unknown | AE name | 투자 유치 확인 필요 |
| Demo Industrial Group | Demo Group, 산업 그룹 C | unknown | unknown |  |  | unknown | AE name | DX/AX 관심 |
| Demo Enterprise Group | DemoGroup, 엔터프라이즈 그룹 D | using | Enterprise Grid | 3000 | 2600 | 2026-12-31 | AE name | attrition risk monitor |
```

## Field Guidance

- `account`: Primary customer or prospect name.
- `aliases`: Search aliases, including Korean, English, product, and legal entity names.
- `current_slack_status`: `using`, `not_using`, `unknown`, `former_user`, or `evaluating`.
- `plan`: Free, Pro, Business+, Enterprise Grid, Enterprise+, unknown, or custom.
- `licensed_users`: contracted, paid, licensed, or billable users when available.
- `active_users`: active users or monthly active users when available. Clarify definition if it is not monthly active users.
- `renewal_date`: Use `YYYY-MM-DD` when known.
- `owner`: AE, CSM, or account owner.
- `notes`: Strategic context, known stakeholders, recent conversations, or restrictions.
