[🇬🇧 English](README.md) | [🇯🇵 日本語](README.ja.md)

# VRM Chat Room

**VRM 모델 기반 멀티 아바타 3D 채팅방 — WebSocket 실시간 메시징, 말풍선, Mixamo 애니메이션 리타겟팅.**

> [NVatar](https://github.com/nskit-io/nvatar) 프로젝트에서 추출 — 로컬 하드웨어에서 완전히 구동되는 AI 아바타 채팅 시스템.

---

## 왜 만들었나

Ready Player Me가 종료되었습니다. VRM 생태계에는 모던 웹에서 **3D 아바타 채팅방**이 어떤 모습인지 보여주는 간결한 데모가 없습니다. 무거운 메타버스 프레임워크는 있지만(VerseEngine, Third Room), 다음 4가지를 경량으로 통합한 구현은 없습니다:

1. **VRM 아바타** — three-vrm으로 렌더링
2. **WebSocket** — 실시간 멀티유저 채팅
3. **말풍선** — 3D 아바타 머리 위에 떠다니는
4. **Mixamo FBX** — VRM 스켈레톤으로 애니메이션 리타겟팅

## 주요 기능

### 3D 아바타 시스템
- **VRM 1.0** 모델, @pixiv/three-vrm 3.3.3
- **자동 눈깜빡임**: 랜덤한 자연스러운 눈깜빡임 간격
- **유휴 호흡**: 미세한 척추 및 신체 움직임
- **시선 추적**: 부드러운 보간 시선 추적

### 감정 포즈
VRM 표정 + 뼈대 회전 블렌드:

| 감정 | 몸 | 표정 |
|------|-----|------|
| 기쁨 | 팔 뒤로, 척추 뒤로 | 미소 블렌드셰이프 |
| 슬픔 | 어깨 앞으로, 척추 굽힘, 고개 숙임 | 슬픔 블렌드셰이프 |
| 분노 | 주먹 쥠, 척추 뒤로 | 분노 블렌드셰이프 |
| 놀람 | 팔 위로, 뒤로 젖힘 | 놀람 블렌드셰이프 |

### Mixamo FBX 리타겟팅
- Mixamo FBX 로드 → 위치 트랙 제거 (회전만)
- 정확한 본 매핑을 위한 커스텀 레스트 포즈 보정 알고리즘
- 포함 모션: Idle, Walking

### 말풍선 시스템
- 3D 머리 위치 → `camera.project()` → 2D 화면 좌표
- 버블 큐: 시간 제한 표시 + 페이드 전환

### 가상 방
- 3D 환경: 벽(3면), 나무 바닥, 창문 + PointLight, 가구
- 더블클릭 이동: 레이캐스터 → 3D 타겟 → 걸기 애니메이션 → 도착 시 유휴

## 기술 스택

| 구성요소 | 기술 |
|----------|------|
| 3D 엔진 | Three.js 0.160 |
| VRM | @pixiv/three-vrm 3.3.3 |
| 애니메이션 | Mixamo FBX |
| 실시간 | WebSocket |

## 관련 프로젝트

- [**avatar-chat**](https://github.com/nskit-io/avatar-chat) — Gemma 캐릭터 AI 프롬프트 엔지니어링 패턴
- [**chat-like-human-memory**](https://github.com/nskit-io/chat-like-human-memory) — 8D 감정 추적 + 성격 진화 + 3단계 기억
- [**customize-local-llm**](https://github.com/nskit-io/customize-local-llm) — 성격은 로컬 Gemma, 팩트는 클라우드 Claude
- [**CSW**](https://github.com/nskit-io/csw) — 클라우드 레이어를 구동하는 Claude Subscription Worker

## 라이선스

MIT License - [LICENSE](LICENSE) 참조

---

## 이 프로젝트를 지원해주세요

NVatar는 AI 아바타 인터랙션의 차세대를 구축하는 독립 R&D 프로젝트입니다. 1인 대표가 외부 투자 없이 진행하고 있습니다.

**후원 및 투자 문의**
- Email: [nskit@nskit.io](mailto:nskit@nskit.io)
- Organization: [NSKit](https://nskit.io) by Neoulsoft Inc.

<p align="center">
  <a href="https://github.com/nskit-io">github.com/nskit-io</a>
</p>
