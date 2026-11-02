# my-skills_assignment · lecture-notes

긴 강의 자료를 **실무 핵심 개념 노트**로 정리해 주는 Claude Code 스킬입니다.

## 왜 만들었나

### 불편했던 점
강의를 들으면서 매번 양이 많아서 요약을 요청하는데 클로드에게 같은 부탁을 반복하는게 불편했습니다.

> "이 내용을 함축해서 실무에서 중요한 개념과 그 개념이 뭔지에 대한 설명을 노트에 정리하기 편하게 정리해줘."

이렇게 매번 부탁하면 생기는 문제는 다음과 같았습니다.
- 같은 요청 문장을 레슨마다 다시 써야 했습니다.
- 그날그날 결과 형식이 달라서 노트끼리 비교하거나 복습하기 어려웠습니다. 어떤 날은 표가 있고, 어떤 날은 용어 정리가 빠졌습니다.
- 원문에 없는 내용이 섞이지 않았는지 매번 직접 확인해야 했습니다.

### 스킬로 해결한 방법
`SKILL.md`에 정리 절차, 출력 형식, 작성 규칙, 점검표를 한 번만 적어 두었습니다.
- 이제 원문을 붙여넣고 **"노트로 정리해 줘"** 한마디만 하면 스킬이 실행됩니다.
- 모든 레슨 노트가 **같은 형식**으로 나옵니다: 한 줄 요약 → 주제별 섹션 → 핵심 용어표 → 실무 원칙 → 템플릿
- "원문에 없는 사실은 쓰지 않는다", "숫자·명령어는 바꾸지 않는다" 같은 규칙이 기본으로 적용될겁니다.

## 구조

```
my-skills_assignment/
├── README.md
└── .claude/skills/lecture-notes/SKILL.md
```

## 설치 방법

개인 스킬 폴더(`~/.claude/skills/`)에 복사하면 **모든 프로젝트에서** 쓸 수 있습니다. 내 터미널에 맞는 명령을 차례대로 입력하세요.

### Windows (PowerShell, VS Code 기본 터미널)

```powershell
git clone https://github.com/xktkf147/my-skills_assignment.git
```

```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\skills"
```

```powershell
Copy-Item -Recurse -Force my-skills_assignment\.claude\skills\lecture-notes "$HOME\.claude\skills\"
```

설치 확인 (`SKILL.md`가 보이면 성공):

```powershell
dir "$HOME\.claude\skills\lecture-notes"
```

### Mac / Linux / Git Bash

```bash
git clone https://github.com/xktkf147/my-skills_assignment.git
```

```bash
mkdir -p ~/.claude/skills
```

```bash
cp -r my-skills_assignment/.claude/skills/lecture-notes ~/.claude/skills/
```

복사한 뒤에는 Claude Code를 다시 시작해야 스킬이 인식됩니다.

- PowerShell에서는 `mkdir -p`, `cp -r`이 다르게 동작하니 위의 Windows용 명령을 쓰세요.
- 특정 프로젝트에서만 쓰려면 `~/.claude/skills/` 대신 `<프로젝트 폴더>/.claude/skills/`에 복사하면 됩니다.

## 사용법 (호출 문장)

새 대화에서 강의 원문을 붙여넣고 아래처럼 말하면 됩니다.

- "이거 노트로 정리해 줘"
- "핵심"
- "요약"
- `/lecture-notes` (직접 호출)
- /lecture-notes
  (강의 원문 붙여 넣기) 이런 식으로 사용하시면 됩니다.

## 확인한 결과

이 저장소를 연 상태에서 **새 Claude Code 세션**을 시작해 시험했습니다.
- 넣은 원문: 모듈 06 강의 중 컨텍스트 창·토큰 비용 단락
- 요청: "아래 강의 내용을 노트로 정리해 줘."
- 결과 1: 스킬 이름을 따로 말하지 않았는데 `lecture-notes` 스킬이 자동으로 선택·실행되었습니다.
- 결과 2: "한 줄 요약 → 개념별 섹션(정의·중요한 이유) → 토큰 비교표 → 핵심 용어표 → 실무 원칙" 형식의 노트가 나왔습니다.
- 결과 3: 원문의 수치(에이전트 약 4배, 멀티 에이전트 약 15배)가 바뀌지 않고 그대로 유지되었습니다.

## 주의

- 스킬에는 인증 정보나 개인 데이터가 들어 있지 않습니다.
- 유료 강의 원문을 공개 저장소에 올리지 마세요. 스킬은 원문을 저장하지 않습니다.
