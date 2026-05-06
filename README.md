# paper-proofread

한국어 학술 논문 교정교열용 Claude Code 스킬입니다.
문서를 청크 단위로 쪼개 맞춤법 · 띄어쓰기 · 문장 교열 · 논리 구조 · 인용/참고문헌까지 점검하고, 수정 원고와 교정교열표를 출력합니다.

---

## 설치 방법

VSCode에 Claude Code 익스텐션이 깔려 있다는 가정 하에, **Claude에게 자연어로 말하면 됩니다.**

### 한 줄 가이드 (글로벌 + 프로젝트 양쪽 설치)

Claude Code 채팅창에 그대로 붙여넣으세요:

```
이 깃허브 레포를 클로드 스킬로 깔아줘. 글로벌이랑 이 프로젝트 양쪽 다 설치해줘:
https://github.com/Eunhye890/paper-proofread
```

Claude가 알아서 두 곳에 클론합니다:

- **글로벌**: `~/.claude/skills/paper-proofread/` → 모든 프로젝트에서 사용 가능
- **프로젝트**: `<현재 프로젝트>/.claude/skills/paper-proofread/` → 이 프로젝트에서만 사용

설치 후 **Claude Code 새 세션을 열면** 스킬이 자동 인식됩니다.

---

### 폴백: 자연어가 잘 안 통할 때

Claude가 위 문장을 못 알아들으면 아래 명령어를 그대로 말해주세요.

**Windows (PowerShell)**

```powershell
git clone https://github.com/Eunhye890/paper-proofread.git $HOME\.claude\skills\paper-proofread
git clone https://github.com/Eunhye890/paper-proofread.git .\.claude\skills\paper-proofread
```

**Mac / Linux**

```bash
git clone https://github.com/Eunhye890/paper-proofread.git ~/.claude/skills/paper-proofread
git clone https://github.com/Eunhye890/paper-proofread.git ./.claude/skills/paper-proofread
```

---

## 사용 방법

설치 후 새 Claude Code 세션에서 아래와 같이 말하면 스킬이 자동 트리거됩니다.

```
이 논문 교정교열해줘 [파일 첨부]
```

```
이 문장 맞춤법이랑 띄어쓰기 좀 봐줘:
"본 연구에서는 데이타를 분석되어지고 있다."
```

```
투고 전에 원고 한 번 다듬어줘.
```

트리거 키워드: `교정`, `교열`, `교정교열`, `proofreading`, `논문 검토`, `논문 수정`, `원고 다듬기`, `맞춤법 검사`, `투고 전 검토`, `문장 교열`, `학술 글쓰기 점검`

---

## 출력물

스킬이 실행되면 다음 세 가지를 받게 됩니다:

1. **교정교열표** — 위치 / 심각도 / 유형 / 원문 / 수정안 / 사유
2. **수정 반영 원고** — 마크다운(또는 요청 시 .docx)
3. **요약 리포트** — 총 수정 건수, 반복 패턴, 전반 평가

심각도 3단계: 🔴 error (반드시 수정) / 🟡 suggest (수정 권고) / 🔵 style (선택적)

---

## 폴더 구조

```
paper-proofread/
├── SKILL.md              # 스킬 본체
├── references/
│   └── rules_ko.md       # 한국어 교정 규칙
└── README.md
```

---

## 제거 방법

Claude에게 말하세요:

```
글로벌이랑 이 프로젝트에 깔려있는 paper-proofread 스킬 폴더를 지워줘.
```
