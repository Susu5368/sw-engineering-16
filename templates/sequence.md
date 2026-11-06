---
번호: XX
기능명: 기능명
담당: 이름
요구사항: requirements/req-XX.md
---

# seq-XX 기능명

## 참여 객체

| 객체 | 종류 | 클래스 파일 |
|---|---|---|
| 담당객체이름 | 담당 객체 | classes/XXX.md |
| 공통객체이름 | 공통 객체 | classes/XXX.md |
| ○○DB | DB | classes/XXX.md |
| 학생UI | UI | classes/StudentUI.md |

## 다이어그램

시작 방식에 맞는 첫 줄 하나만 남긴다.

```mermaid
sequenceDiagram
    %% 시작점 (하나만 사용)
    participant Found as ●
    %% actor 시간
    %% participant 학생UI

    participant 담당 as 담당객체이름
    participant DB1 as ○○DB
    participant UI as 학생UI

    Found->>+담당: 1: ~됨(모임ID: int)
    담당->>DB1: 2: ~조회(모임ID: int): List<int>
    DB1-->>담당: 결과이름
    alt 조건
        Note over 담당: 아무것도 하지 않고 종료
    else
        담당->>담당: 3: ~계산(값: int): double
        담당->>DB1: 4: ~저장(모임ID: int, 결과목록: List<엔티티>)
        담당-)UI: 5: ~알림(학생ID: int)
    end
    deactivate 담당
```

## 메시지 ↔ Action 대응표

| 메시지 | Action |
|---|---|
| 1~2 | 1 |
| 3 | 2 |

## 작성 전 체크

- [ ] 객체 이름이 GLOSSARY 표기와 같다 (공백·약어 없음)
- [ ] 시작 메시지가 규칙(5.2)에 맞다
- [ ] 메시지 이름 끝말이 규칙(5.3)에 맞다
- [ ] 모든 매개변수가 `이름: 자료형`이고 자료형이 허용 목록에 있다
- [ ] Action의 if-else가 alt/opt로, 반복이 loop로 표현됐다
- [ ] 대응표를 썼다
- [ ] 받는 클래스 파일에 연산을 반영했다
