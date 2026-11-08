# 대학 강의실 3D

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
