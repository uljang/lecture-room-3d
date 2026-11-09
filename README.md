# 머스크의 구조교실

3×5 책상 배치의 대학 강의실을 앞에서 두 번째 줄 가운데 자리에서 둘러보는 3D 웹 뷰어입니다.

바로 보기: https://uljang.github.io/lecture-room-3d/

- 드래그/터치: 고개 돌리기 (양옆·뒤쪽까지)
- 방향키 또는 WASD: 회전, 휠: 확대
- Space: 일어서기/앉기, R: 정면

## 교수 아바타
- `teacher_web.glb`: teacher.glb 의 웹용 사본 (텍스처만 2048px JPEG로 축소, 81MB → 4.9MB)
- GLB 안의 `Talk_with_Hands_Open` 클립을 Talking으로 사용하고, 없는 Idle / Waving / Pointing 은 코드로 생성합니다.
- 교수님 클릭: 손 흔들기, 화이트보드·스크린 클릭: 가리키기
- 로컬에서 html 파일을 직접 열면(file://) GLB를 불러올 수 없어 웹 링크로 확인해야 합니다.

## 강의 진행
- 화면 아래 자막과 이전/다음 버튼으로 단계 이동 (키보드: N·Enter·PageDown 다음, P·PageUp 이전)
- 강의 내용은 `index.html` 맨 위의 `window.LECTURE` 데이터만 고치면 바뀝니다 (say / board.title / board.points / board.diagram)
- 새 칠판 내용이 있으면 Pointing 후 칠판에 판서, 말하는 동안 Talking, 끝나면 Idle
- 강의 중에는 화이트보드가 보이도록 프로젝터 스크린이 말려 올라갑니다

## 퀴즈 · 배속
- 자막 배속 1x / 1.5x / 2x / 3x
- 강의 끝에 객관식 퀴즈 3문제: 아래 보기 버튼, 칠판의 보기 클릭, 숫자키 1~4로 답하기
- 정답이면 GLB의 춤 클립(Breakdance_1990, FunnyDancing_02)을 번갈아 재생, 오답이면 해설 + 다시 풀기 버튼 (틀린 보기는 지워지고 남은 보기에서 다시 고름)

## 여러 강의
- 시작 화면 또는 아래 바의 `강의 목록`에서 강의를 고름
- 기본 강의: `lectures/*.js` (새 파일을 만들고 index.html 맨 위 `<script src>` 목록에 한 줄 추가)
- 화면에서 추가: `+ 강의 자료 추가`로 JSON 파일을 올리거나 시작 화면에 끌어다 놓기 (브라우저에 저장, 삭제 가능)
- 예시 JSON: `lectures/sample-simple-beam.json`, 양식은 `선택한 강의 JSON 받기`로 받을 수 있음

## 노트 필기 · 질문하기
- `노트` 버튼 또는 책상 위 노트를 클릭: 펜(검정/파랑/빨강), 형광펜, ⌨ 타자(노트를 누른 줄에 글자 입력, 쓴 글자를 누르면 수정), 지우개, 되돌리기, 여러 쪽, 칠판 받아 적기, 이미지로 저장. 필기는 강의별로 브라우저에 저장되고 책상 위 3D 노트에도 보임
- `✋ 질문하기`: 기본은 강의 내용 + `lectures/common-faq.js` 용어집에서 찾아 답함. 강의 파일에 `faq: [...]`를 넣으면 강의 전용 질문 추가
- AI 설정에 본인 Claude API 키를 넣으면 Claude Opus 5.5가 강의 내용을 바탕으로 답함 (키는 브라우저에만 저장, Anthropic API로 직접 호출, 요금은 키 주인 부담)
