# 1.1 tmux 설치 및 기본

## 핵심 개념

- **세션 (Session)**: 독립된 작업 환경, 백그라운드에서 유지됨
- **윈도우 (Window)**: 세션 안의 탭
- **패널 (Pane)**: 윈도우 안에서 화면 분할

## 필수 명령어

```bash
# 세션 관리
tmux new -s 이름      # 새 세션 만들기
tmux ls               # 세션 목록
tmux attach -t 이름   # 세션 들어가기
tmux kill-session -t 이름  # 세션 강제 종료

# 세션 안에서 (Ctrl+b = prefix)
Ctrl+b, d             # detach (빠져나오기)
Ctrl+b, s             # 세션 목록 & 전환
exit 또는 Ctrl+d      # 세션 종료
```

## 멀티 에이전트 협업에서 쓰임

```
tmux new -s main      # 메인 오케스트레이터
tmux new -s worker1   # 워커 1
tmux new -s worker2   # 워커 2
...

Ctrl+b, s 로 세션 간 빠르게 전환
```
